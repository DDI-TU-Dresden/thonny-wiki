Using Pygame in Thonny
=======================

Thonny 1.3 bundles (and experimental bundles of 1.2) will have Pygame preinstalled, but don't contain all Pygame requirements on all platforms. This page explains how to install these.

Windows
--------
Windows installer contains Pygame together with all requirements. Pygame should be ready to use after installing Thonny.

Mac OS X
---------
Mac OS X bundle contains Pygame and the requirements (eg. SDL and co). 



Linux
--------

Linux bundle contains Pygame itself but not the libraries required by it (SDL and co.). Fortunately popular distros have a Pygame package meant for Python 2, which we can use for installing Pygame dependencies. It doesn't matter whether you install this package before or after installing Thonny.

Ubuntu, Mint, Debian
~~~~~~~~~~~~~~~~~~~~~~~~~

.. sourcecode:: bash

    sudo apt-get install python-pygame


CentOS 7
~~~~~~~~~~~~~~ 

CentOS official repos don't contain the package for Pygame, but see http://li.nux.ro/repos.html and http://pkgs.org/download/pygame. 

In order to add 

.. sourcecode:: bash

    sudo yum -y install epel-release
    sudo rpm -Uvh http://li.nux.ro/download/nux/dextop/el7/x86_64/nux-dextop-release-0-5.el7.nux.noarch.rpm
    sudo yum -y install pygame


