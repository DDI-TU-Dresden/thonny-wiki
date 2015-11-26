Install Python and Thonny separately
=====================================
If there is no Thonny+Python bundle for your operating system or you can't or don't want to use it, you can first install Python (or use your existing Python) and then install Thonny in the context of this Python installation.

General steps
--------------

1. Install Python 3.4 or later (or use an existing installation).
2. Install Thonny package with ``pip`` using your operating system command line.
3. Run Thonny package.


Mac OS X
-----------
If you don't have Python 3.4 or later installed, then go to https://www.python.org/downloads/mac-osx/ and install latest Python 3.5 from there.

For installing Thonny as package, you need to go to system command line and execute something like ``pip install thonny``, but you need to make sure command ``pip`` is related to correct Python installation.

For opening system command line: 

1. open Finder
2. from the menu choose Go => Utilities
3. open "Terminal"

Assuming you are using official Python 3.5 distribution, paste into Terminal 

.. sourcecode:: bash

    sudo /Library/Frameworks/Python.framework/Versions/3.5/bin/pip3.5 install thonny

and press ENTER. Enter your password when requested.

If you don't have admin rights, then you can install the package only for your user:

.. sourcecode:: bash

    /Library/Frameworks/Python.framework/Versions/3.5/bin/pip3.5 install --user thonny


Updating Tcl/Tk (optional)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
If you don't use Thonny+Python bundle, but install Thonny into an existing Python, then it relies also on existing Tcl/Tk. This version of Tcl/Tk may be old, which means you may see Thonny crashing too often. (Python's IDLE has similar problems, see https://www.python.org/download/mac/tcltk)

The solution is to install newer version. Go to http://www.activestate.com/activetcl/downloads and download and install the latest 8.5 version of ActiveTcl. (Most likely your Python is linked with Tk 8.5. If IDLE-s about dialog says it uses 8.6, then install latest ActiveTcl 8.6)