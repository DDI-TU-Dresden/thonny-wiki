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
    yum -y install zlib-devel bzip2-devel openssl-devel ncurses-devel sqlite-devel readline-devel gdbm-devel db4-devel libpcap-devel xz-devel



Prepare directory for custom TclTk and Python. Let's chooce a nice path, because frozen Python modules will remember this location as their location. End user may see these locations in stacktraces.

.. sourcecode:: bash

    mkdir /opt/pythonny
    chmod 777 /opt/pythonny # if you want to do next steps as ordinary user

Build TclTk 8.6
----------------

.. sourcecode:: bash

    cd tcl8.6/unix
    ./conigure --prefix=/opt/pythonny
    make
    make install

    cd tk8.6/unix
    ./conigure --prefix=/opt/pythonny
    make
    make install

Build Python
-------------

set LD_LIBRARY_PATH (https://mail.python.org/pipermail/tkinter-discuss/2011-March/002808.html)


.. sourcecode:: bash

    # set LD_LIBRARY_PATH (https://mail.python.org/pipermail/tkinter-discuss/2011-March/002808.html)
    export LD_LIBRARY_PATH=/opt/pythonny/lib
    
    # compile and install Python
    cd Python-3.5.0
    ./conigure --prefix=/opt/pythonny --with-tcltk-includes=I/opt/pythonny/include --with-tcltk-libs=L/opt/pythonny/lib
    make
    make install
    
    /opt/pythonny/bin/python3.5 -m idlelib # check that it uses Tk 8.6

Install cx_Freeze
-----------------
4.3.4 does not work with Python 3.5, use a newer version (eg. from repo: 

.. sourcecode:: sh

    cd anthony_tuininga-cx_freeze-aebc9c32615c/
    /opt/pythonny/bin/python3.5 setup.py install




