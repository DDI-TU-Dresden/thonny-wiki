Thonny on Linux
========================
Thonny and Python bundle should work on:

* Mint 13 Maya (glibc-2.15)
* Debian 8 Jessie (glibc-2.19)
* Ubuntu 12.04 precise (glibc-2.15)
* Opensuse 13.1 (glibc-2.19)
* Fedora 21 (glibc-2.20)
* CentOS 7.1 (glibc-2.17)

or newer.

It may run on even older versions, but precompiled Thonny is linked against glibc-2.12, therefore the (only?) requirement is that the distro should be with glibc-2.12 or newer. 

Requirements
----------------------
Thonny needs Python 3.4 or later with tkinter and IDLE. Necessary packages for some distros (eg. Ubuntu) are ``python3``, ``python3-tk`` and ``python3-idle`` (if ``python3-idle`` doesn't exist then try ``idle3``), for some (eg. Fedora) these are ``python3`` and ``python3-tools``.


Installing
------------

`Download <https://bitbucket.org/plas/thonny/downloads>`_ the file with tar.gz extension, unpack and run the installation script. For example, in Ubuntu command line you could execute following commands:

.. sourcecode:: none

    > tar -zxvf thonny-1.0.5.tar.gz
    > cd thonny-1.0.5
    > sudo ./install

If you would like to install it only for your user (perhaps because you don't have admin acces to the machine you're using), then you can tell installer to install thonny to some folder under your home folder. For example, instead of ``sudo ./install`` you would say:

.. sourcecode:: none

    > ./install ~/my_programs

In either way, you should see something like this:

.. sourcecode:: none

    Checking available Python versions ................................... Done!
    Thonny will use Python 3.4
    Copying files to /opt/thonny ......................................... Done!
    Creating start menu item (/usr/share/applications/Thonny.desktop) .... Done!
    Creating uninstaller (/opt/thonny/bin/uninstall) ..................... Done!

    Installation was successful, you can start Thonny from start menu under
    Education or Programming, or by calling /opt/thonny/bin/thonny
    
Note
~~~~~~
For some reason, in Lubuntu 15.04, when you install under /home (and shortcut gets installed into ~/.local/share/applications), Thonny item doesn't appear in start menu. The workaround is to install with sudo into default directory.

Uninstalling
------------------------
Excecute the uninstall command shown by the installer, eg. 

.. sourcecode:: none

    > sudo /opt/thonny/bin/uninstall
