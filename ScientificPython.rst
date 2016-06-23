Using Scientific Python with Thonny
==================================

Python distribution coming with Thonny doesn't contain scientific programming libraries (eg. `NumPy <http://numpy.org/>`_  and `Matplotlib <http://matplotlib.org/>`_). Installing them and their dependencies can be tricky, but fortunately you can install a separate scientific Python distribution (eg. `Anaconda <https://www.continuum.io/downloads>`_, `Canopy <https://www.enthought.com/products/canopy/>`_ or `Pyzo <http://www.pyzo.org/>`_) and let Thonny use this for running your programs.

Example: Using Anaconda with Thonny
------------------------------------
Go to https://www.continuum.io/downloads and download a suitable binary distribution for your platform. Most likely you want graphical installer and 64-bit version (you may need 32-bit version if you have very old system). Note that although Thonny runs only on Python 3, you can use both Python 3 and Python 2 versions of Anaconda with it (if you don't know which one to choose, then pick Python 3 version).

Install it and find out where it puts Python executable (`pythonw.exe` in Windows and `python3` or `python` in Linux and Mac). For example in Windows the full path is by default *c:\anaconda\pythonw.exe*.

In Thonny open "Tools" menu and select "Options ...". In the options dialog open "Intepreter" tab, click "Select executable" and show the location of Anaconda's Python executable.

After you have done this, next time you run your program, it will be run through Anaconda's Python and all the libraries installed there are available.