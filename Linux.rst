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


It may run on even older versions, but precompiled Thonny is linked against glibc-2.12, therefore the (only?) requirement is that the distro should be with glibc-2.12 or newer. 





Installing
------------

`Download <https://bitbucket.org/plas/thonny/downloads>`_ the file with tar.gz extension, unpack and run the installation script. For example, in Ubuntu command line you could execute following commands:

.. sourcecode:: none

    > tar -zxvf thonny-1.1.0b7-x86_64.tar.gz
    > cd thonny
    > ./install

If you would like to install to a specific location, then you can specify parent folder for Thonny folder eg:

.. sourcecode:: none

    > sudo ./install /opt

Uninstalling
------------------------
Excecute the uninstall command shown by the installer, eg. 

.. sourcecode:: none

    > sudo /opt/thonny/bin/uninstall


Alternative
----------------------
If you can't install or run bundled Thonny, then try `install Python and Thonny separately <SeparateInstall>`_.



