Thonny on Linux
========================

Requirements
----------------------
Thonny needs Python 3.4 or later with tkinter and IDLE. Necessary packages for some distros (eg. Ubuntu) are ``python3``, ``python3-tk`` and ``python3-idle`` (if ``python3-idle`` doesn't exist then try ``idle3``), for some (eg. Fedora) these are ``python3`` and ``python3-tools``.


Installing
------------

`Download <https://bitbucket.org/plas/thonny/downloads>`_ the file with tar.gz extension, unpack and run the installation script. For example, in Ubuntu command line you could run following commands:

.. sourcecode:: none

    > tar -zxvf thonny-1.0.5.tar.gz
    > cd thonny-1.0.5
    > sudo ./install

If you would like to install it only for your user (perhaps because you don't have admin acces to the machine you're using), then you can tell installer to install thonny to some folder under your home folder:

.. sourcecode:: none

    > tar -zxvf thonny-1.0.5.tar.gz
    > cd thonny-1.0.5
    > ./install ~/my_programs

In either way, you should see something like this:

.. sourcecode:: none

    Checking available Python versions ................................... Done!
    Thonny will use Python 3.4
    Copying files to /opt/thonny ......................................... Done!
    Creating start menu item (/usr/share/applications/Thonny.desktop) .... Done!
    Creating uninstaller (/opt/thonny/bin/uninstall) ..................... Done!

    Installation was successful, you can start Thonny from start menu
    or by calling /opt/thonny/bin/thonny
    

Uninstalling
------------------------
Excecute the uninstall command shown in by the installer, eg. 

.. sourcecode:: none

    > sudo /opt/thonny/bin/thonny
