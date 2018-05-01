# Plug-ins

**NB! Plug-in system was changed in 2.2 and may still change during the beta phase.**

Thonny can be extended with 3rd party plug-ins. Usually they are distributed via https://pypi.org and can be installed with Tools => Mangage plug-ins.

## Writing plug-ins

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

## Location of the plug-ins



## What can a plug-in (ie. function ``load_plugin``) do?

In short: whatever. 

More pragmatically: ``load_plugin`` usually retrieves the singleton instance of the class ``thonny.workbench.Workbench`` and calls its public methods like ``add_command`` or ``add_syntax_theme`` with suitable arguments.


## Back-end plug-ins

TODO:

## How to package and distribute your plug-in?

In short: same way as you would package and distribute any Python module or package.

TODO: expand this 

## Built-in plug-ins

Built-in plug-ins are located under ``thonny.plugins``.