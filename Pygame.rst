Using Pygame in Thonny
=======================

(Future) Thonny bundles for Linux (will) have Pygame preinstalled, but don't contain Pygame requirements. This page explains how to install these.

Ubuntu, Mint, Debian
------------------------

.. sourcecode:: bash

    sudo apt-get install python-pygame


CentOS 7
------------

.. sourcecode:: bash

    sudo yum -y install epel-release
    sudo rpm -Uvh http://li.nux.ro/download/nux/dextop/el7/x86_64/nux-dextop-release-0-5.el7.nux.noarch.rpm
    sudo yum -y install pygame


(More info: http://li.nux.ro/repos.html and http://pkgs.org/download/pygame)
