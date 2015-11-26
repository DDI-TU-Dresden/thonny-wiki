Using Thonny on Mac OS X
=========================

Installation
-------------
Requirements
-------------
Thonny+Python bundle is supported on OS X 10.9 Mavericks and later. On older systems you can use `universal install <universal>`_.



Installation
-----------------

Download latest *.dmg file and open it. You should see a small window with single icon labeled "Thonny" in it.

.. image:: https://bitbucket.org/repo/gXnbod/images/766784258-Screen%20Shot%202015-11-26%20at%2011.53.51.png
   :alt: Screen Shot 2015-11-26 at 11.53.51.png

Drag the icon to your Desktop or Applications folder, where you can open it by double clicking.

First obstacle: Most likely your Mac refuses to run Thonny, because I haven't paid Apple 99$ per year to prove that I'm a trustworthy developer :p
Current workaround is that first time you run Thonny by Ctrl-clicking or right-clicking, selecting "Open" and selecting again "Open" in confirmation dialog. Alternative: go to System settings, open "Security & Privacy" and make it "Allow applications downloaded from anywhere" (you may need to click on the padlock before you can edit that setting). 


Updating Tcl/Tk (optional)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
If you don't use Thonny+Python bundle, but install Thonny into an existing Python, then it relies also on existing Tcl/Tk. This version of Tcl/Tk may be old, which means you may see Thonny crashing too often. (Python's IDLE has similar problems, see https://www.python.org/download/mac/tcltk)

The solution is to install newer version. Go to http://www.activestate.com/activetcl/downloads and download and install the latest 8.5 version of ActiveTcl. (Most likely your Python is linked with Tk 8.5. If IDLE-s about dialog says it uses 8.6, then install latest ActiveTcl 8.6)