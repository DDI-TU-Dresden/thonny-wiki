Theming
=======

Since version 2.2 Thonny supports UI themes, which allow changing the appearance of widgets, and Syntax themes, which allow specifying coloring scheme for editors and the shell. A couple of themes are built into Thonny (see "Tools => Options => Theme & Font", but users can add their own themes via the `plug-in system <Plugins>`_.

Adding a syntax theme
------------------------
Let's say you mostly like the built-in "Desert Sunset" theme, but you wish the keywords had lighter color and regular weight and current line was more pronounced. In this case it you can write a plug-in which adds a new syntax theme  (let's call it "Desert Sunset Plus"), which is based on "Desert Sunset" but changes aforementioned properties.

A plug-in can add a new syntax theme via workbench method ``add_syntax_theme``. You need to pass a unique name, name of the parent theme and a dictionary specifying visual properties for syntactical elements to be overridden. (Instead of the dictionary you can also provide a parameterless callable returning the dictionary -- this may speed up the process of adding (unused) syntax themes.)

When you start enhancing a theme, you probably want to start by looking up theme's original properties. All built-in syntax themes are defined in ``thonny.plugins.base_syntax_themes``. Locate this file and find the line with 

The plug-in implementing "Desert Sunset Plus" could be something like this: