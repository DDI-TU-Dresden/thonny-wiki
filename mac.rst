Mac issues
===========

Installation
-----------------

Download latest *.dmg file and open it. You should see a small window with single icon labeled "Thonny" in it. Drag the icon to your Desktop or Applications folder, where you can open it by double clicking.

First obstacle: Most likely your Mac refuses to run Thonny, because I haven't paid Apple 99$ per year to prove that I'm a trustworthy developer :p
Current workaround is that you go to System settings, open "Security & Privacy" and make it "Allow applications downloaded from anywhere" (you may need to click on a padlock before you can edit that setting). After this you should be able to run Thonny (but first time you still need to confirm your will).

Tk issues
-------------
Thonny relies on something called Tcl/Tk, that is installed on Macs but usually the version that is installed is not good one, which means you will see Thonny crashing too often. (Python's IDLE has similar problems, see https://www.python.org/download/mac/tcltk)

The solution is to install the good version. Go to http://www.activestate.com/activetcl/downloads and download and install the latest 8.5 version of ActiveTcl. NB! The version should **start with 8.5** (at the time of this writing it's 8.5.15). Version 8.6 (most likely) won't work.

Required Python version
-------------------------
Currently Thonny requires Python 3.4 to be installed.
