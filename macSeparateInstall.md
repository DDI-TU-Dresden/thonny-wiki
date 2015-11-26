Mac OS X - Install Python and Thonny separately
================================================
TODO:


Updating Tcl/Tk (optional)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
If you don't use Thonny+Python bundle, but install Thonny into an existing Python, then it relies also on existing Tcl/Tk. This version of Tcl/Tk may be old, which means you may see Thonny crashing too often. (Python's IDLE has similar problems, see https://www.python.org/download/mac/tcltk)

The solution is to install newer version. Go to http://www.activestate.com/activetcl/downloads and download and install the latest 8.5 version of ActiveTcl. (Most likely your Python is linked with Tk 8.5. If IDLE-s about dialog says it uses 8.6, then install latest ActiveTcl 8.6)