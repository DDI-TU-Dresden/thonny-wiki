Linux
==========

Prepare requisites
------------------
On CentOS (as root):

.. sourcecode:: bash

    yum -y update
    yum -y groupinstall 'Development Tools'

    # From http://toomuchdata.com/2014/02/16/how-to-install-python-on-centos/
    # (yes, I include tk-devel even though I'll compile a newer version later. This seems to bring along nicer fonts in tkinter)
    yum -y install zlib-devel bzip2-devel openssl-devel ncurses-devel sqlite-devel readline-devel gdbm-devel db4-devel libpcap-devel xz-devel libX11-devel tk-devel

On Ubuntu:
http://askubuntu.com/questions/21547/what-are-the-packages-libraries-i-should-install-before-compiling-python-from-so

.. sourcecode:: bash

    sudo apt-get update
    sudo apt-get upgrade
    sudo apt-get install git mercurial # needed below
    sudo apt-get build-dep python # may work, but probably installs too much
    sudo apt-get install build-essential libncursesw5-dev libreadline6-dev libssl-dev libgdbm-dev libc6-dev libsqlite3-dev tk-dev libbz2-dev lzma-dev liblzma-dev python-lzma lzma xz-utils xz-lzma

Prepare directory for custom TclTk and Python. Let's chooce a nice path, because frozen Python modules will remember this location as their location. End user may see these locations in stacktraces.

.. sourcecode:: bash

    mkdir /opt/pythonny
    chmod 777 /opt/pythonny # if you want to do next steps as ordinary user

Build TclTk 8.6
----------------
Get sources from http:// www.tcl.tk/software/tcltk/download.html or http://sourceforge.net/projects/tcl/files/.

On Linux:

.. sourcecode:: bash

    wget http://prdownloads.sourceforge.net/tcl/tcl8.6.4-src.tar.gz
    tar -xzf tcl8.6.4-src.tar.gz
    cd tcl8.6.4/unix
    ./configure --prefix=/opt/pythonny
    make install
    cd ../..

    wget http://prdownloads.sourceforge.net/tcl/tk8.6.4-src.tar.gz
    tar -xzf tk8.6.4-src.tar.gz
    cd tk8.6.4/unix
    # see http://sourceforge.net/p/tktoolkit/bugs/2588/ for --disable-xss
    ./configure --prefix=/opt/pythonny --disable-xss # add --enable-aqua on Mac
    make install
    cd ../..


On Mac:
https://mail.python.org/pipermail/python-list/2014-June/674026.html

.. sourcecode:: bash

    wget http://prdownloads.sourceforge.net/tcl/tcl8.6.4-src.tar.gz
    tar -xzf tcl8.6.4-src.tar.gz
    cd tcl8.6.4/unix
    ./configure --enable-framework
    sudo make install NATIVE_TCLSH=/usr/local/bin/tclsh8.6
    cd ../..

    wget http://prdownloads.sourceforge.net/tcl/tk8.6.4-src.tar.gz
    tar -xzf tk8.6.4-src.tar.gz
    cd tk8.6.4/unix
    # see http://sourceforge.net/p/tktoolkit/bugs/2588/ for --disable-xss
    ./configure --enable-framework --enable-aqua --disable-xss
    sudo make install NATIVE_TCLSH=/usr/local/bin/tclsh8.6
    cd ../..


Build tkhtml (required for some Thonny plug-ins):
Get source from http://tkhtml.tcl.tk/ or https://github.com/olebole/tkhtml3 (or https://github.com/hkoba/tkhtml3)

.. sourcecode:: bash

    # Generate some source files (see readme in https://github.com/starseeker/tcltk/tree/master/tkhtml)
    /opt/pythonny/bin/tclsh8.6 src/cssprop.tcl 
    /opt/pythonny/bin/tclsh8.6 src/tokenlist.txt 
    /opt/pythonny/bin/tclsh8.6 src/mkdefaultstyle.tcl > htmldefaultstyle.c
    
    # copy these generated files to src
    mv *.c src
    mv *.h src
    
    # create build dir
    mkdir build
    cd build
    
    # configure, make and install
    ../configure --prefix=/opt/pythonny --with-tcl=/opt/pythonny/lib --with-tk=/opt/pythonny/lib --with-tclinclude=/opt/pythonny/include --with-tkinclude=/opt/pythonny/include
    make install






Build Python
-------------

On Linux:

.. sourcecode:: bash

    wget https://www.python.org/ftp/python/3.5.0/Python-3.5.0.tar.xz
    tar xf Python-3.5.0.tar.xz 
    cd Python-3.5.0
     
    # set LD_LIBRARY_PATH (https://mail.python.org/pipermail/tkinter-discuss/2011-March/002808.html)
    export LD_LIBRARY_PATH=/opt/pythonny/lib

    # compile and install Python
    ./configure --prefix=/opt/pythonny --with-tcltk-includes=-I/opt/pythonny/include --with-tcltk-libs=-L/opt/pythonny/lib
    make altinstall
    
    # check that the newly built Python uses Tk 8.6 for Tkinter
    /opt/pythonny/bin/python3.5 -m idlelib 

On Mac:

TODO: First check that Tk8.6 is Current.


.. sourcecode:: bash

    wget https://www.python.org/ftp/python/3.5.0/Python-3.5.0.tar.xz
    tar xf Python-3.5.0.tar.xz 
    cd Python-3.5.0
     
    # compile and install Python
    ./configure --enable-framework
    sudo make frameworkinstall
    
    # check that the newly built Python uses Tk 8.6 for Tkinter
    /Library/Frameworks/Python.framework/Versions/3.5/bin/python3.5 -m idlelib 

Install cx_Freeze
-----------------
4.3.4 does not work with Python 3.5, use a newer version (eg. from repo): 

.. sourcecode:: sh

    hg clone https://bitbucket.org/anthony_tuininga/cx_freeze
    cd cx_freeze
    /opt/pythonny/bin/python3.5 setup.py install



Checkout and freeze Thonny 
----------------------------

.. sourcecode:: sh
    
    # It matters for stacktraces where Thonny is frozen
    cd /opt/pythonny

    git clone https://bitbucket.org/plas/thonny
    cd thonny/installers/linux/
    ./create_frozen_tarball.sh


Test it:

.. sourcecode:: sh
    
    ./build/thonny-1.1.0b1/thonny_frontend

Build Pygame
-------------
http://www.pygame.org/wiki/CompileUbuntu

.. sourcecode:: sh
    
    #install dependencies (without python3-numpy suggested in Pygame wiki)
    sudo apt-get install mercurial python3-dev libav-tools \
        libsdl-image1.2-dev libsdl-mixer1.2-dev libsdl-ttf2.0-dev libsmpeg-dev \
        libsdl1.2-dev  libportmidi-dev libswscale-dev libavformat-dev libavcodec-dev
     
    # Grab source
    hg clone https://bitbucket.org/pygame/pygame
     
    # Finally build and install
    cd pygame
    /opt/pythonny/bin/python3.5 setup.py install
