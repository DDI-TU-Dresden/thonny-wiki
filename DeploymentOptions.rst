========================
Deployment options
========================

Default
--------
Main Thonny+Python bundles are meant to be installed by the end user. Because of this Windows installer does not require admin privileges and installs under `%LOCALAPPDATA%\Programs` by default.

Independently of Thonny main files' location, on first run it creates a directory named `.thonny` in user home directory, which is used for storing user configuration, plug-ins and 3rd party packages the user has installed. For organizing the 3rd party packages Thonny generates a virtual environment.

With this scheme the user can update the main program without losing his or her customizations.

Classroom
----------
If the computer lab supports persistent user profiles and users' disk quota is not too small, then the default deployment scheme, ie. **each students installs Thonny himself/herself**, should be suitable also in classroom setting. (Depending on your lab set-up you may want to recommend students to install into `%APPDATA%\Programs` instead of `%LOCALAPPDATA%\Programs`.)

If you can't use persistent profiles, then you can **preinstall Thonny either locally or to a network drive**. In Windows you can use Thonny installer, but note that it does not request admin privileges even if you enter a restricted target directory, so you may want to run it as administrator. Alternatively you can install Thonny under your own profile and then copy its program folder (by default `C:\Users\<username>\AppData\Local\Programs\Thonny`) into a central location. In both cases you probably also want to create the shortcuts for all users.