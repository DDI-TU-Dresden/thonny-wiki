Thonny on Linux
========================


Requirements
----------------------
Thonny and Python bundle should work on these Linuxes or newer:

* Mint 13 Maya
* Debian 8 Jessie
* Ubuntu 12.04 precise
* Opensuse 13.1
* Fedora 21
* CentOS 7.1


Why these? Precompiled binaries are linked against glibc-2.12, therefore the (only?) requirement is that the distro should be with glibc-2.12 or newer. If you can't install or run bundled Thonny, then try to `install Python and Thonny separately <SeparateInstall>`_.



Installing
------------

`Download <https://bitbucket.org/plas/thonny/downloads>`_ the file with tar.gz extension. If you have 64-bit Linux, then use file with x86_64 suffix, otherwise use the one with i686 suffix (run ``uname -m`` in terminal if you are not sure which you have). Unpack the file and run the installation script. For example, in Ubuntu command line you could execute following commands:

.. sourcecode:: none

    > tar -zxvf thonny-1.1.0b7-x86_64.tar.gz
    > cd thonny
    > ./install

This will install Thonny under *apps* directory in your home directory. If you would like to install to a specific location, then you can specify parent folder for Thonny folder eg:

.. sourcecode:: none

    > sudo ./install /opt

Uninstalling
------------------------
Excecute the uninstall command shown by the installer, eg. 

.. sourcecode:: none

    > sudo /opt/thonny/bin/uninstall






