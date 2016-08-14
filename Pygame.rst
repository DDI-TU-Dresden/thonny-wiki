(Obsoloete page) Using Pygame in Thonny (Obsoloete page) 
========================================================

.. note::

    Following text is not relevant anymore as Pygame can now be installed with pip

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

Compiling in Fedora 24
-----------------------
There is package *python3-pygame* but this will won't install for Thonny's python.

.. sourcecode:: bash

    sudo dnf groupinstall 'Development Tools' 'C Development Tools and Libraries'
    sudo dnf install redhat-rpm-config wget python-devel SDL_image-devel SDL_mixer-devel SDL_ttf-devel SDL-devel numpy mercurial portmidi-devel freetype-devel libpng-devel libjpeg-devel

    wget ftp://ftp5.gwdg.de/pub/opensuse/repositories/home:/zhonghuaren/Fedora_23/x86_64/smpeg-0.4.5-8.1.x86_64.rpm
    wget ftp://ftp5.gwdg.de/pub/opensuse/repositories/home:/zhonghuaren/Fedora_23/x86_64/smpeg-devel-0.4.5-8.1.x86_64.rpm
    sudo dnf install smpeg*.rpm
    rm smpeg*.rpm

    hg clone https://bitbucket.org/pygame/pygame
    cd pygame

    export PORTMIDI_INC_PORTTIME=1 # https://bitbucket.org/pygame/pygame/pull-requests/65/allow-for-portmidi-library-to-contain/diff#comment-None
    sudo touch /etc/timidity.cfg # Othewise playing midi will give error

    wget http://www.libsdl.org/projects/SDL_mixer/timidity/timidity.tar.gz


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

If you have trouble running yum because of PackageKit, then see http://ask.xmodulo.com/disable-packagekit-centos-fedora-rhel.html

Compiling in CentOs 7
~~~~~~~~~~~~~~~~~~~~~~~~~~~


.. sourcecode:: bash

    sudo yum groupinstall 'Development Tools'
    sudo yum install wget python-devel SDL_image-devel SDL_mixer-devel SDL_ttf-devel SDL-devel numpy mercurial portmidi-devel freetype-devel libpng-devel libjpeg-devel

    wget ftp://ftp.pbone.net/mirror/ftp5.gwdg.de/pub/opensuse/repositories/home:/Kenzy:/packages/CentOS_7/x86_64/smpeg-0.4.5-2.4.x86_64.rpm
    wget ftp://ftp.pbone.net/mirror/ftp5.gwdg.de/pub/opensuse/repositories/home:/Kenzy:/packages/CentOS_7/x86_64/smpeg-devel-0.4.5-2.4.x86_64.rpm
    sudo yum --nogpgcheck install smpeg*.rpm
    rm *.rpm

    export PORTMIDI_INC_PORTTIME=1 # https://bitbucket.org/pygame/pygame/pull-requests/65/allow-for-portmidi-library-to-contain/diff#comment-None
    sudo touch /etc/timidity.cfg # Othewise playing midi will give error

Compiling
-----------------

.. sourcecode:: bash

    sudo apt-get build-dep python-pygame 
    yum-builddep package_name

Installing with pip
------------------------
Thonny Tools => Open system shell

.. sourcecode:: bash

    python3.5 -m pip install hg+http://bitbucket.org/pygame/pygame