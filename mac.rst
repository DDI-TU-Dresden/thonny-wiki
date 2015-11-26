Using Thonny on Mac OS X
=========================

Requirements
-------------
Thonny+Python bundle is supported on OS X 10.9 Mavericks and later. On older systems you can use `universal install <universal>`_.



Installation
-------------------------------------

Download latest *.dmg file and open it. You should see a small window with single icon labeled "Thonny" in it.

.. image:: https://bitbucket.org/repo/gXnbod/images/3178666057-Screen%20Shot%202015-11-26%20at%2011.55.30.png
   :alt: Screen Shot 2015-11-26 at 11.55.30.png

Drag the icon to your Desktop or Applications folder. This will copy Thonny to your computer. 

.. image:: https://bitbucket.org/repo/gXnbod/images/3987278567-Screen%20Shot%202015-11-26%20at%2012.02.09.png
   :alt: Screen Shot 2015-11-26 at 12.02.09.png

When copying has finished, you can close the original small window by Ctrl-clicking (or right-clicking) and selecting "Eject":

.. image:: https://bitbucket.org/repo/gXnbod/images/3393714686-Screen%20Shot%202015-11-26%20at%2012.04.04.png
   :alt: Screen Shot 2015-11-26 at 12.04.04.png

Now you can (try to) run Thonny by double-clicking its icon on Desktop or Applications folder. Most likely first time your Mac refuses running it, because I haven't paid Apple 99$ per year to prove that I'm a trustworthy developer :p

.. image:: https://bitbucket.org/repo/gXnbod/images/127107093-Screen%20Shot%202015-11-26%20at%2012.08.36.png
   :alt: Screen Shot 2015-11-26 at 12.08.36.png

If this happens, you should Ctrl-click (or right-click) the icon and select "Open" from context menu:

.. image:: https://bitbucket.org/repo/gXnbod/images/3915137553-Screen%20Shot%202015-11-26%20at%2012.11.36.png
   :alt: Screen Shot 2015-11-26 at 12.11.36.png

You will get a confirmation dialog where you should click "Open":

...

You may need to provide password for your (or admin) account. (If you don't have admin rights, then you can use `this little trick <MacWithoutAdminRights>`_ to make your Mac believe the application didn't come from the internet.)

Opening Thonny first time may take several seconds, because Thonny needs to prepare it's files.

Finally you should see Thonny window. Next time you open Thonny, everything should go without any confirmations and much faster.

Updating Tcl/Tk (optional)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
If you don't use Thonny+Python bundle, but install Thonny into an existing Python, then it relies also on existing Tcl/Tk. This version of Tcl/Tk may be old, which means you may see Thonny crashing too often. (Python's IDLE has similar problems, see https://www.python.org/download/mac/tcltk)

The solution is to install newer version. Go to http://www.activestate.com/activetcl/downloads and download and install the latest 8.5 version of ActiveTcl. (Most likely your Python is linked with Tk 8.5. If IDLE-s about dialog says it uses 8.6, then install latest ActiveTcl 8.6)