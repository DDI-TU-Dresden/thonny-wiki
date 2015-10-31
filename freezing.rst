Linux
==========

Prepare requisites
------------------
On CentOS (as root):

.. sourcecode:: bash

    yum -y update
    yum -y groupinstall 'Development Tools'

    # From http://toomuchdata.com/2014/02/16/how-to-install-python-on-centos/
    # (I excluded tk-devel, because I want newer Tk anyway)
    yum -y install zlib-devel bzip2-devel openssl-devel ncurses-devel sqlite-devel readline-devel gdbm-devel db4-devel libpcap-devel xz-devel libX11-devel



Prepare directory for custom TclTk and Python. Let's chooce a nice path, because frozen Python modules will remember this location as their location. End user may see these locations in stacktraces.

.. sourcecode:: bash

    mkdir /opt/pythonny
    chmod 777 /opt/pythonny # if you want to do next steps as ordinary user

Build TclTk 8.6
----------------

.. sourcecode:: bash

    cd tcl8.6/unix
    ./configure --prefix=/opt/pythonny/
    make install

    cd tk8.6/unix
    ./configure --prefix=/opt/pythonny/
    make install

Build Python
-------------



.. sourcecode:: bash

    wget https://www.python.org/ftp/python/3.5.0/Python-3.5.0.tar.xz
    tar xf Python-3.5.0.tar.xz 
    cd Python-3.5.0
     
    # set LD_LIBRARY_PATH (https://mail.python.org/pipermail/tkinter-discuss/2011-March/002808.html)
    export LD_LIBRARY_PATH=/opt/pythonny/lib

    # compile and install Python
    ./configure --prefix=/opt/pythonny --with-tcltk-includes=I/opt/pythonny/include --with-tcltk-libs=L/opt/pythonny/lib
    make altinstall
    
    # check that newly built Python uses Tk 8.6 for Tkinter
    /opt/pythonny/bin/python3.5 -m idlelib 

Install cx_Freeze
-----------------
4.3.4 does not work with Python 3.5, use a newer version (eg. from repo: 

.. sourcecode:: sh

    cd anthony_tuininga-cx_freeze-aebc9c32615c/
    /opt/pythonny/bin/python3.5 setup.py install



Checkout and freeze Thonny 
----------------------------

.. sourcecode:: sh
    
    # It matters for stacktraces where Thonny is frozen
    cd /opt/pythonny

    git clone https://bitbucket.org/plas/thonny
    cd thonny/installers/linux/
    ./create_frozen_tarball.sh

    # test it
    ./build/thonny-1.1.0b1/thonny_frontend

