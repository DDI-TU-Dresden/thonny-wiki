Installing extra packages
============================

Starting with Thonny 1.3.0b4 it's possible to install new Python packages with *pip*:

#. From "Tools" menu select "Open system shell". You should get a new terminal window stating the correct name of *pip* command (usually ``pip`` or ``pip3``). In the following I've assumed the command name is ``pip``.
#. Enter ``pip install <package name>`` (eg. ``pip install pygame``) and press ENTER. You should see *pip* downloading and installing the package and printing a success message.
#. Close the terminal (optional)
#. Return to Thonny
#. Reset interpreter by selecting "Stop/Reset" from "Run menu" (this is required only first time you do pip install)
#. Start using the package

Under the hood
--------------
If you use Thonny's built in Python, then pip installs packages inside .thonny directory under your home directory. This way you don't need to reinstall the packages when you update Thonny.

Using scientific Python packages
----------------------------------
Recent versions of most popular scientific Python packages (eg. numpy, pandas and matplotlib) have wheels available for popular platforms so you can most likely install them with pip but in case you have troubles, you could try using Thonny with `separate Python distribution meant for scientific computing <ScientificPython>`_.