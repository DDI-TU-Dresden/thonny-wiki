Plug-ins
=========

Thonny can be extended with 3rd party plug-ins. Usually they are distributed via https://pypi.org and can be installed with Tools => Mangage plug-ins.

Writing plug-ins
-----------------
A 3rd-party Thonny plug-in is a Python module (or package) located under ``thonnycontrib`` (or ``thonnycontrib.backend``) namespace package and containing parameterless function ``load_plugin``. 

During startup Thonny locates all such modules and calls their ``load_plugin`` function.

For Thonny's plug-in mechanism, this is really all there is to be said. Plug-in writers, of course, want to know what they can do in ``load_plugin`` and how to package and distribute their work.


What can a plug-in (ie. function ``load_plugin``) do?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
In short: whatever. 

More pragmatically: ``load_plugin`` usually retrieves the singleton instance of the class ``thonny.workbench.Workbench`` and calls its public methods like ``add_command`` or ``add_syntax_theme`` with suitable arguments.

TODO: document Workbench API

Back-end plug-ins
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
TODO:

How to package and distribute your plug-in?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
In short: same way as you would package and distribute any Python module or package.

TODO: expand this 

Built-in plug-ins
~~~~~~~~~~~~~~~~~~~~~~ 
Built-in plug-ins are located under ``thonny.plugins``.