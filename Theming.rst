Theming
=======

**NB! Theming system may change, especially during the beta phase of Thonny 2.2!**

Since version 2.2 Thonny supports UI themes, which allow changing the appearance of widgets, and Syntax themes, which allow specifying coloring scheme for editors and the shell. A couple of themes are built into Thonny (see "Tools => Options => Theme & Font", but users can add their own themes via the `plug-in system <Plugins>`_.

Adding a syntax theme
------------------------
Let's say you mostly like the built-in "Desert Sunset" theme, but you wish the keywords had lighter foreground and regular weight and current line was more pronounced. In this case it you can write a plug-in which adds a new syntax theme  (let's call it "Desert Sunset Plus"), which is based on "Desert Sunset" but changes aforementioned properties.

A plug-in can add a new syntax theme via workbench method ``add_syntax_theme``. You need to pass a unique name for your theme, name of the parent theme and a dictionary specifying visual properties for syntactical elements to be overridden. (Instead of the dictionary you can also provide a parameterless function returning the dictionary -- this way you can postpone computing the properties on theme loading time.)

Let's first inspect the original theme. All built-in syntax themes are defined in ``thonny.plugins.base_syntax_themes``. Locate this file and find the line with ``get_workbench().add_syntax_theme("Desert Sunset", "Default Dark", desert_sunset)``. As we see it's parent theme is "Default Dark" and it provides properties as a function. After investigating the properties of "Desert Sunset" and "Default Dark", you could come up with a plug-in like this:

The plug-in implementing "Desert Sunset Plus" could be something like this:

.. sourcecode:: py3

    from thonny import get_workbench

    def load_plugin():
        get_workbench().add_syntax_theme("Desert Sunset Plus", "Desert Sunset", {
            "keyword"       : {"foreground" : "#DE8C3A", "font" : "EditorFont"},
            "current_line"  : {"background" : "#525252"},
        })

Look around in ``thonny.plugins.base_syntax_themes`` to learn about available syntactic and other elements and their configuration options.

UI Themes
----------
In order to create a new UI theme you need to first look around in ``thonny.plugins.base_ui_themes`` and ``thonny.plugins.clean_ui_themes``.
 
In general you should be familiar with Tkinter (or Tk) ttk styles unless you just want to create a derivative of "Clean Dark" or "Clean Light" (in this case I'm sure you can figure out from the examples of "Clean Dark Green" and friends).