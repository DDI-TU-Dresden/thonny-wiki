Using Thonny in classrooms
==========================
...

Windows
--------
Thonny installer doesn't require admin privileges. This is supposed to allow the students to install Thonny also into classroom computers where they have restricted access.

Default **installation path** is ``%LOCALAPPDATA%\Programs\Thonny`` (eg. ``C:\Users\Aivar\AppData\Local\Programs\Thonny``). Depending on the setup of your classroom, it may make sense to install Thonny under `%APPDATA%` (eg. ``C:\Users\Aivar\AppData\Roaming\Thonny``). If you want to choose a directory outside %USERPROFILE% then you may need to  run the installer as administrator.

It is OK to install Thonny into one directory and then copy the installation directory to another place, eg. to a network location. This way you can create a shared installation in the classroom. With this approach you currently need to create the shortcuts by yourself, though.

On first run Thonny creates a user-specific directory for storing configuration and default virtual environment for executing user programs. By default its path is ``%USERPROFILE%\.thonny`` (eg. ``C:\Users\Aivar\.thonny``). This may change in future versions (see #279), but you can change it already by running Thonny with environment variable ``THONNY_USER_DIR`` pointing to desired location.

customize.py
------------
One option for specifying ``THONNY_USER_DIR`` is to create a bat-file which sets it and then runs Thonny. Since version 2.1.10 you can alternatively create a script named ``customize.py`` under ``thonny`` package (eg. ``C:\Users\Aivar\AppData\Local\Programs\Thonny\Lib\site-packages\thonny``) which makes desired changes in the environment:


.. sourcecode:: python

    import os
    os.environ["THONNY_USER_DIR"] = "<path to desired folder>"
    

If present, this script is run as first step of launching Thonny.

user_dir_template
-----------------
Since version 2.1.10 you can tell Thonny how it should initialize its user directories (THONNY_USER_DIR). For this you should create a directory named ``user_dir_template`` under ``thonny``-package (eg. ``N:\ClassroomNetworkPrograms\Thonny\Lib\site-packages\thonny``). 

For example, if you want students' programs to use bundled python.exe directly (instead of creating a virtual environment), you should put a ``configuration.ini`` under ``user_dir_template``, which looks something like this:


.. sourcecode:: ini

    [run]
    backend_configuration = Python (N:\ClassroomNetworkPrograms\Thonny\python.exe)