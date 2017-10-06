==========================
Portable version of Thonny
==========================
Thonny doesn't depend on its installation location: you can copy its program directory (eg. ``C:\Users\...\AppData\Local\Programs\Thonny in Windows``) to another location (including a flash stick) and it should work without problems. 

This allows you to make Thonny's main program portable. In order to avoid regenerating user directory each time you use Thonny in new computer, you need to do some more tweaking.

THONNY_USER_DIR + customize.py
-------------------------------
By default Thonny keeps its configuration files, default virtual environment and plugins under ``~/.thonny``. You can change this with THONNY_USER_DIR environment variable.

If you want to make THONNY_USER_DIR relative to program directory, then you should take advantage of the possibility to customize Thonny's startup. You should create a file named *customize.py* in Thonny package directory (eg. ``C:\Users\...\AppData\Local\Programs\Thonny\Lib\site-packages\thonny``) and create the environment variable in there:


.. sourcecode:: python

    import os.path
    
    # Compute desired location for user directory
    user_dir = os.path.join(os.path.dirname(__file__), "..", "..", "..", ".thonny")
    os.environ["THONNY_USER_DIR"] = os.path.abspath(user_dir)

Don't use default (virtual environment) interpreter
----------------------------------------------------
The remaining problem is that by default Thonny generates a virtual environment for running your programs. The virtual environment is related to the base interpreter through an absolute path. Fortunately Thonny allows you to specify different backend instead of the default venv (Tools => Options => Interpreter). Since version 2.1.12 you can specify there that back-end interpreter should be the same as front-end interpreter (in older versions you could browse the correct interpreter, but this would result in absolute path).