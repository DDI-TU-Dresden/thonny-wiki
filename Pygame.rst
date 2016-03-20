Using Pygame in Thonny
=======================

Thonny bundles starting with 1.3 (and already some experimental bundles of 1.2) have Pygame preinstalled. In Windows and Mac Pygame should work out-of-the-box.

Linux bundle contains Pygame itself but not the libraries required by it (SDL and co.). Fortunately popular distros have a Pygame package meant for Python 2, which we can use for installing Pygame dependencies. It doesn't matter whether you install this package before or after installing Thonny.

Ubuntu, Mint, Debian
-----------------------

.. sourcecode:: bash

    sudo apt-get install python-pygame

Fedora
-----------------------

TODO: This needs to be checked

.. sourcecode:: bash

    sudo yum install pygame


CentOS 7
----------------

CentOS official repos don't contain the package for Pygame, but see http://li.nux.ro/repos.html and http://pkgs.org/download/pygame. 

In order to add 

.. sourcecode:: bash

    sudo yum -y install epel-release
    sudo rpm -Uvh http://li.nux.ro/download/nux/dextop/el7/x86_64/nux-dextop-release-0-5.el7.nux.noarch.rpm
    sudo yum -y install pygame


