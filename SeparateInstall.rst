Install Python and Thonny separately
=====================================
If there is no Thonny+Python bundle for your operating system or you can't or don't want to use it, you can first install Python (or use your existing Python) and then install Thonny in the context of this Python installation.

General steps
--------------

1. Install Python 3.4 or later (or use an existing installation).
2. Install Thonny package with ``pip`` using your operating system command line.
3. Run Thonny package.


Windows
--------
If you need separate install, because you are using Windows XP, then you should first install Python 3.4, as later Python versions are not compatible with XP.



Mac OS X
-----------
If you don't have Python 3.4 or later installed, then go to https://www.python.org/downloads/mac-osx/ and install latest Python 3.5 from there.

For installing Thonny as package, you need to go to system command line and execute something like ``pip install thonny``, but you need to make sure command ``pip`` is related to correct Python installation.

For opening system command line: 

1. open Finder
2. from the menu choose Go => Utilities
3. open "Terminal"

Assuming you are using official Python 3.5 distribution, paste following into Terminal and press ENTER:

.. sourcecode:: bash

    /Library/Frameworks/Python.framework/Versions/3.5/bin/pip3.5 install thonny

You should see something like this:

.. image:: https://bitbucket.org/repo/gXnbod/images/4031047622-Screen%20Shot%202015-11-26%20at%2014.24.23.png
   :alt: Screen Shot 2015-11-26 at 14.24.23.png

Now you can run Thonny with following command:

.. sourcecode:: bash

    /Library/Frameworks/Python.framework/Versions/3.5/bin/python3.5 -m thonny


**Updating Tcl/Tk (optional)**. *Thonny relies on something called Tcl/Tk. Your Python installation may use too old Tcl/Tk version, which means you may see Thonny crashing too often or doing weird things. (Python's IDLE has similar problems, see https://www.python.org/download/mac/tcltk). The solution is to install newer version. Go to http://www.activestate.com/activetcl/downloads and download and install the latest 8.5 version of ActiveTcl. (Most likely your Python is linked with Tk 8.5. If IDLE-s about dialog says it uses 8.6, then install latest ActiveTcl 8.6)*