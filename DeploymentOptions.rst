========================
Deployment options
========================

Single user
------------
Main Thonny+Python bundles are designed to be installed by the end user. Therefore Windows installer does not require admin privileges and installs under ``%LOCALAPPDATA%\Programs\Thonny`` by default.

Independently of Thonny main files' location, on first run it creates a directory named ``.thonny`` in user home directory, which is used for storing user configuration, plug-ins and 3rd party packages the user has installed. For organizing the 3rd party packages Thonny generates a virtual environment there.

With such scheme the user can easily update the main program without losing the customizations.

Classroom
----------
If the computer lab supports persistent user profiles and users' disk quota is big enough, then the **single user** deployment scheme is suitable also in classroom setting. (Depending on your lab set-up you may want to recommend students to install into ``...\AppData\Roaming\...`` instead of ``...\AppData\Local\...``.)

If you can't use persistent profiles, then you can **preinstall Thonny either locally or to a network drive**. In Windows you can use Thonny installer, but note that it does not request admin privileges even if you enter a restricted target directory, so you may want to run it as administrator. Alternatively you can install Thonny under your own profile and then copy its program folder (by default ``C:\Users\<username>\AppData\Local\Programs\Thonny``) into a shared location. In both cases you probably also want to create the shortcuts for all users.

Even if the main program is installed centrally, by default Thonny still creates a virtual environment under user home (if it doesn't exist yet). If you want to avoid this, then you can configure Thonny to **use the front-end interpreter** (ie. the same Python executable it uses for running the GUI) also for the back-end (ie. for running user programs). 

You could **pre-configure Thonny** for all users by arranging a suitable ``configuration.ini`` in their ``.thonny`` directory. Since version 2.1.10 you can do it by letting Thonny know how to initialize the user directory (THONNY_USER_DIR). For this you should create a directory named ``user_dir_template`` under ``thonny``-package (eg. ``P:\ClassroomNetworkPrograms\Thonny\Lib\site-packages\thonny``). 

For example, if you want students' programs to use bundled python.exe directly (instead of creating a virtual environment), you should put a ``configuration.ini`` under ``user_dir_template``, which looks something like this:

.. sourcecode:: ini

    [run]
    backend_configuration = Python (N:\ClassroomNetworkPrograms\Thonny\python.exe)

Since version 2.1.12 you can use a special macro ``same as front-end``:

.. sourcecode:: ini

    [run]
    backend_configuration = Python (same as front-end)


Don't forget that you can also use a separate Python installation for the backend:

.. sourcecode:: ini

    [run]
    backend_configuration = Python (C:\Python36\python.exe)


Preparing shared 3rd party packages and plug-ins
------------------------------------------------
You can arrange your shared Thonny so that the students can start off with same set of 3rd party packages.

If you want your students to use **their own virtual environments** (ie. you are using the default back-end), then you should use the regular tools ("Tools => Manage packages ..." and "Tools => Manage plug-ins...") to prepare a suitable ``.thonny`` directory in your computer and then copy it into shared ``user_dir_template`` (see previous section). NB! Check the ``home`` variable in ``.thonny\BundledPython36\pyvenv.cfg`` to make sure students can access Thonny directory with the same path!

If you have configured Thonny to **use the main interpreter also for the back-end process**, then you should pip-install the required packages and plug-ins directly into base ``site-packages``. The easiest way for this is to open Thonny with sufficient privileges, select "Tools => Open system shell..." and use command-line pip.

Changing the location of user directory
------------------------------------------------------
Regardless of your deployment scheme, you may want to override the path of Thonny user directory (``%USERPROFILE%\Thonny`` / ``~/.thonny`` by default). This can be done with ``THONNY_USER_DIR`` environment variable. You could create a launch script which sets this variable and then runs Thonny, or you can read further ...


customize.py
-----------------
Since version 2.1.10 Thonny looks for a script named ``customize.py`` under ``thonny`` package (eg. ``C:\Users\Aivar\AppData\Local\Programs\Thonny\Lib\site-packages\thonny``). If present this is run as first step of launching.

You can use this to prepare the environment for Thonny, eg:

.. sourcecode:: python

    import os
    os.environ["THONNY_USER_DIR"] = "H:\\home\\.thonny" 
    
Upgrading shared Thonny
-------------------------
Nothing special here, just replace Thonny program files. Just be careful not to lose your customizations (``customize.py`` and/or ``user_dir_template``).

With micro updates (eg. 2.1.12 => 2.1.14) you should be able to just copy the new files over older ones. With minor and major updates (eg. 2.1.12 => 2.2.0 or 2.1.12 => 3.0) it's safer to discard the old Thonny directory and prepare new from scratch.

Creating a portable version of Thonny
-------------------------------------
You can use the information from previous sections to prepare yourself a portable, USB-stick-ready Thonny.

1) Make THONNY_USER_DIR relative to the main Thonny directory. Following ``customize.py`` should do:

.. sourcecode:: python

    import os.path
    
    user_dir = os.path.join(os.path.dirname(__file__), "..", "..", "..", ".thonny")
    os.environ["THONNY_USER_DIR"] = os.path.abspath(user_dir)

2) Configure Thonny to use front-end interpreter also for the back-end by putting following ``configuration.ini`` into ``.thonny`` (requires version 2.1.12 or later):

.. sourcecode:: ini

    [run]
    backend_configuration = Python (same as front-end)

(The second step is necessary, because the default virtual environment would be connected to base Python via an absolute path)