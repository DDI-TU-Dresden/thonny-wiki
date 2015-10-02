Thonny on Linux
========================

Requirements
----------------------
Thonny needs Python 3.4 or later with tkinter and IDLE. Necessary packages for some distros (eg. Ubuntu) are ``python3``, ``python3-tk`` and ``python3-idle`` (if ``python3-idle`` doesn't exist then try ``idle3``), for some (eg. Fedora) these are ``python3`` and ``python3-tools``.


Installing
------------

`Download <https://bitbucket.org/plas/thonny/downloads>`_ the file with tar.gz extension, unpack and run the installation script. If you would like to install it only for your user (perhaps because you don't have admin acces to the machine you're using), then execute following three commands:

.. sourcecode:: none

    tar -zxvf thonny-0.2.2.tar.gz
    cd thonny-0.2.2
    ./install ~/.local

(If you want to install for all users, then your third command should be something like ``sudo ./install /usr/local``.)

You should see something like this:

.. sourcecode:: none

    Copying files to /home/aivar/.local/lib/thonny ... Done!
    Creating executable /home/aivar/.local/bin/thonny ... Done!
    Creating start menu item ... Done!
    Creating desktop icon ... Done!



Uninstalling
------------------------
Just delete:

* Thonny main folder (in the example above it's ``/home/aivar/.local/lib/thonny``);
* executable (eg. ``/home/aivar/.local/bin/thonny``);
* shortcuts:
    * ``/usr/share/applications/Thonny.desktop`` or ``~/.local/share/applications/Thonny.desktop``
    * ``~/Desktop/Thonny.desktop``
