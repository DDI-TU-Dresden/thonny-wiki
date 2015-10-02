Mac issues
===========

Installation
-----------------

Download latest *.dmg file and open it. You should see a small window with single icon labeled "Thonny" in it. Drag the icon to your Desktop or Applications folder, where you can open it by double clicking.

First obstacle: Most likely your Mac refuses to run Thonny, because I haven't paid Apple 99$ per year to prove that I'm a trustworthy developer :p
Current workaround is that you first time you run Thonny by Ctrl-clicking or right-clicking, selecting "Open" and selecting again "Open" in confirmation dialog. Alternative: go to System settings, open "Security & Privacy" and make it "Allow applications downloaded from anywhere" (you may need to click on a padlock before you can edit that setting). 

Updating Tcl/Tk (optional)
---------------------------
Thonny relies on something called Tcl/Tk, that is installed on Macs but usually the version that is installed is not good one, which means you may see Thonny crashing too often. (Python's IDLE has similar problems, see https://www.python.org/download/mac/tcltk)

The solution is to install the good version. Go to http://www.activestate.com/activetcl/downloads and download and install the latest 8.5 version of ActiveTcl. NB! The version should **start with 8.5** (at the time of this writing it's 8.5.18). At the moment Thonny won't use version 8.6.
