========================
Deployment options
========================

Single user
------------
Main Thonny+Python bundles can be installed by the end user. Because of this Windows installer does not require admin privileges and installs under ``%LOCALAPPDATA%\Programs`` by default.

Independently of Thonny main files' location, on first run it creates a directory named ``.thonny`` in user home directory, which is used for storing user configuration, plug-ins and 3rd party packages the user has installed. For organizing the 3rd party packages Thonny generates a virtual environment.

With this scheme the user can update the main program without losing his or her customizations.

Classroom
----------
If the computer lab supports persistent user profiles and users' disk quota is not too small, then the **single user** deployment scheme should be suitable also in classroom setting. (Depending on your lab set-up you may want to recommend students to install into ``%APPDATA%\Programs`` instead of ``%LOCALAPPDATA%\Programs``.)

If you can't use persistent profiles, then you can **preinstall Thonny either locally or to a network drive**. In Windows you can use Thonny installer, but note that it does not request admin privileges even if you enter a restricted target directory, so you may want to run it as administrator. Alternatively you can install Thonny under your own profile and then copy its program folder (by default ``C:\Users\<username>\AppData\Local\Programs\Thonny``) into a central location. In both cases you probably also want to create the shortcuts for all users.

Even if the main program is installed centrally, by default Thonny still creates a virtual environment under user home (if it doesn't exist yet). If you want to avoid this, then you can configure Thonny to **use the front-end interpreter (ie. the same Python executable it uses for running the GUI) also for the back-end (ie. for running user programs)**. 

You could **pre-configure Thonny** for all users by arranging a suitable ``configuration.ini`` in their ``.thonny`` directory before they first run Thonny, but since version