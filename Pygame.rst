Using Pygame in Thonny
=======================

.. note::

    Thonny bundles older than 1.3 doesn't include Pygame. 

**In Windows and Mac OS X Pygame should work out-of-the-box.**

**Linux** bundles contain Pygame itself but not the libraries required by it (SDL and co.). Fortunately popular distros have a Pygame package meant for Python 2, which we can use for installing Pygame dependencies. It doesn't matter whether you install this package before or after installing Thonny.

Ubuntu, Mint, Debian
-----------------------

.. sourcecode:: bash

    sudo apt-get install python-pygame

openSUSE
-----------------------

.. sourcecode:: bash

    sudo zypper install python-pygame

Fedora
-----------------------

.. sourcecode:: bash

    sudo yum install pygame


Mageia
-------
.. sourcecode:: bash

    sudo urpmi python-pygame

Manjaro, Arch
----------------
.. sourcecode:: bash

    sudo pacman -S python2-pygame

CentOS 7
----------------

CentOS official repos don't contain the package for Pygame, but see http://li.nux.ro/repos.html and http://pkgs.org/download/pygame. 

In the following we add a new repo and install Pygame:

.. sourcecode:: bash

    sudo yum -y install epel-release
    sudo rpm -Uvh http://li.nux.ro/download/nux/dextop/el7/x86_64/nux-dextop-release-0-5.el7.nux.noarch.rpm
    sudo yum -y install pygame


