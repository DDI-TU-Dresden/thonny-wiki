Writing Thonny plugins
=========================

TODO: This is just a draft

Example
--------
Let's make a plugin which adds a view to Thonny.

1. Clone (or fork) Thonny

2. In *thonny/plugins* create file called *fortune.py* with following content:

.. sourcecode:: py3

    # TODO: https://helloacm.com/api/fortune/

3. (Re)start Thonny and you should see a new view ...

Explanation
-----------
Plugins go to folder *thonny/plugins*.

A plugin can be a simple module (*.py file) or a package (a directory containing __init__.py). The module (or the top namespace of the package) must contain a function called ``load_plugin`` which takes instance of ``thonny.workbench.Workbench`` as an argument. The return value will be ignored.

Events
------
Thonny uses two kinds of events: Tkinter events and Workbench events. ...