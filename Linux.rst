========================
Thonny on Linux
========================

Installing via distribution's package manager
----------------------------------------------

* **Raspbian** since Stretch comes with Thonny preinstalled. On older Raspbians try ``sudo apt-get install thonny``.
* **Fedora** since 27: ``sudo dnf install thonny``

**NB! We're looking for contributors, who are willing to package Thonny for other distros!**

Installing prebuilt Thonny+Python bundles
-----------------------------------------
Thonny and Python bundle should work on these Linuxes or newer:

* Mint 13 Maya
* Debian 8 Jessie
* Ubuntu 12.04 precise
* Opensuse 13.1
* Fedora 21
* CentOS 7.1


It may run on other distros/versions, but the requirement is that the distro should be with *glibc-2.15* or newer.

(If you can't install or run bundled Thonny, then try to `install Python and Thonny separately <SeparateInstall>`_.)


Installing
~~~~~~~~~~~~
If you want to install latest bundle with default settings, then execute following command in terminal: 

.. sourcecode:: none

    > bash <(curl -s http://thonny.org/installer-for-linux)

This script downloads and unpacks suitable installer for your platform and executes it.

Alternative way for installing
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
If you want more control, then you can do the install steps separately.

`Download <https://bitbucket.org/plas/thonny/downloads>`_ the file with tar.gz extension. If you have 64-bit Linux, then use file with x86_64 suffix, otherwise use the one with i686 suffix (run ``uname -m`` in terminal if you are not sure which you have).

Unpack the file and run the installation script.For example, in Ubuntu command line you could execute following commands:


.. sourcecode:: none

    > tar -zxvf thonny-1.1.0b7-x86_64.tar.gz
    > cd thonny
    > ./install

This will install Thonny under *apps* directory in your home directory. If you would like to install to a specific location, then you can specify parent folder for Thonny folder eg:

.. sourcecode:: none

    > sudo ./install /opt

Uninstalling
~~~~~~~~~~~~~~~~~~~~ 
Excecute the uninstall command shown by the installer, eg. 

.. sourcecode:: none

    > sudo /opt/thonny/bin/uninstall