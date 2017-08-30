Portable version of Thonny
==========================
You can copy Thonny program directory (eg. ``C:\Users\...\AppData\Local\Programs\Thonny in Windows``) to another location (including a flash stick) and it should work without problems. 

By default Thonny keeps its configuration files, default virtual environment and plugins under ``~/.thonny``. You can change this with THONNY_USER_DIR environment variable. 

If you want to make THONNY_USER_DIR relative to program directory, then you should take advantage of the possibility to customize Thonny's startup. You should create a file named *customize.py* in Thonny package directory (eg. ``C:\Users\...\AppData\Local\Programs\Thonny\Lib\site-packages\thonny``) and create the environment variable in there:


.. sourcecode:: python

    import os.path
    
    # Compute desired location for user directory
    user_dir = os.path.join(os.path.dirname(__file__), "..", "..", "..")
    os.environ["THONNY_USER_DIR"] = os.path.abspath(user_dir)