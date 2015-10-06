Windows specific issues
==================================

Requirements
-------------
Thonny is supported on Windows 7 and later.

Starting with version 1.0 Thonny comes with an embedded Python, so you don't need to install Python separately.

Installing
-----------------
The installing and uninstalling procedures are really standard, nothing much to say about this.

The slightly unusual thing with Windows installer is that it doesn't request admin privileges to run (but see the section on SmartScreen Filter). This way students can install it on their lab computers at school without bugging the administrator. Without admin privileges it's not possible to install under Program Files, that's why installer proposes a folder under current user's home folder. (BTW, Microsoft now recommends per user installs, look for "*The recommended default installation context is per-user*" in http://msdn.microsoft.com/en-us/library/aa367559%28v=vs.85%29.aspx)

Windows 8, 10 and SmartScreen Filter
-------------------------------------
Windows 8 and 10 include a feature called SmartScreen Filter, which tries to reduce the risk of users installing malware into their computers. See http://www.howtogeek.com/123938/htg-explains-how-the-smartscreen-filter-works-in-windows-8/ for more info.

Short story is that currently Windows 8 and 10 may be suspicious about Thonny installer and may call it "unsafe". In Windows 8, the warnings are strongest when the installer is downloaded and run via Internet Explorer (if downloaded and run with eg. Firefox, you see the usual confirmation you've accustomed to see in previous Windows versions).