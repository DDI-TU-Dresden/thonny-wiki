# Plug-ins

**NB! Plug-in system was changed in 3.0**

Thonny can be extended with 3rd party plug-ins. Usually they are distributed via https://pypi.org and can be installed with Tools => Mangage plug-ins.

## About writing plug-ins

A 3rd-party Thonny plug-in is a Python module (or package) located under `thonnycontrib` (or `thonnycontrib.backend`) [namespace package](https://packaging.python.org/guides/packaging-namespace-packages/) and containing parameterless function ``load_plugin``.

Here's an example of a plug-in which adds a command into "Tools" menu:

```
from thonny import get_workbench
from tkinter.messagebox import showinfo

def hello():
    showinfo("Hello!", "Thonny rules!")

def load_plugin():
    get_workbench().add_command(command_id="hello",
                                menu_name="tools",
                                command_label="Hello!",
                                handler=hello)
```

During startup Thonny locates all such modules and calls their `load_plugin` function.

## Setting up the development

Where does aforementioned `thonnycontrib` package live? As it is a [namespace package](https://packaging.python.org/guides/packaging-namespace-packages/), it can be spread out to several places on Python path. This means you can either use a directory which is already on Python path or you can create your project anywhere and run Thonny with project directory added to the path.

If you don't want to mess with the path then it's easiest to develop and test the plug-in under `~/.thonny/plugins/Python??/site-packages/thonnycontrib`. If this directory doesn't exist yet, then I recommend to install an existing plugin first -- this will create the proper directory. As a quick test, save the example plug-in code from above to `hello.py` in this folder. When you now (re)start Thonny, you should see a new item in Tools-menu.

NB! In current master and in releases starting from 2.2b5 the location `~/.thonny/plugins/` will be replaced by the directory where your `pip install --user` packages go.

### An example setup (with Linux commands)

First make sure you have installed all [required Python packages](https://bitbucket.org/plas/thonny/src/master/requirements.txt?at=master&fileviewer=file-view-default) (either with pip into a virtual environment or via system tools).

Following commands show how to set up both Thonny and your plugin project with the hello plugin shown above. When you run thonny on the last line, you should see the new item in Tools menu.


```
#!bash

cd ~
mkdir thonny_stuff
cd thonny_stuff
git clone https://bitbucket.org/plas/thonny
mkdir -p my_plugin/thonnycontrib
cp hello.py my_plugin/thonnycontrib
export PYTHONPATH=~/thonny_stuff/my_plugin
cd thonny
python3 -m thonny

```



## What can a plug-in do?

In short: whatever. 

More pragmatically: ``load_plugin`` usually retrieves the singleton instance of the class ``thonny.workbench.Workbench`` (using ``thonny.get_workbench()``) and calls its public methods like ``add_command`` or ``add_syntax_theme`` with suitable arguments.

At the moment these methods are not documented, so you need to read the code in `thonny.workbench` and/or some existing plug-ins (either 3rd party plug-ins listed above or built-in plug-ins under `thonny.plugins` package)


## Back-end plug-ins

Regular plug-ins work in Thonny's front-end process, but it's also possible to add plug-ins for CPython back-end. These plug-ins must live under `thonnycontrib.backend`.

TODO: See ____ for an example.

## How to package and distribute your plug-in?

In short: same way as you would package and distribute any Python module or package. Just make sure your distribution name starts with `thonny-` and you have specified supported Thonny version range under dependencies (even if you manage to create a plug-in which works both with Thonny 2.1 and 2.2+). 

TODO: add an example