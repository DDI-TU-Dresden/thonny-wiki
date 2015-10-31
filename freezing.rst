Linux
==========
Prepare directory for custom TclTk and Python

.. sourcecode:: bash

    mkdir /opt/pythonny

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




