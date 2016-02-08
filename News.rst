Version 1.2.0b1 (2016-02-08)
=============================
Single instance
----------------
Previously, when you opened a py file with Thonny, a new Thonny instance (window) was created even if an instance existed already. This became nuisance if you opened several files. Now Thonny now works as single instance program, meaning only one instance of Thonny runs at the time. When you open another file, it is opened in existing window.

Editor enhancements
---------------------
Added option to show line numbers and right margin in the editor. In order to keep first impression cleaner, they are disabled by default. See Tools => Options => Editor. Don't forget that you don't need line numbers for locating lines mentioned in error messages -- you can click them and Thonny shows you the line.

Fixed bugs
-----------
Some bugs were fixed where Thonny couldn't prepare some programs for debugging.

