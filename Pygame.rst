Using Pygame in Thonny
=======================

Thonny bundles for Linux have Pygame preinstalled, but don't contain Pygame requirements. In order to install these, you need to do:

In Ubuntu, Mint, Debian
------------------------

.. sourcecode:: bash

    sudo apt-get install python-pygame


In CentOS 7
------------

.. sourcecode:: bash

    sudo yum -y install epel-release
    sudo rpm -Uvh http://li.nux.ro/download/nux/dextop/el7/x86_64/nux-dextop-release-0-5.el7.nux.noarch.rpm
    sudo yum -y install pygame


Relevant sources:
* http://li.nux.ro/repos.html
* http://pkgs.org/download/pygame
