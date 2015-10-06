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

Short story is that currently Windows 8 and 10 may be suspicious about Thonny installer and may call it "unsafe".

The warnings are strongest when the installer is downloaded and run via Internet Explorer (if downloaded and run with eg. Firefox, you should see the usual confirmation you've accustomed to see in previous Windows versions).

Actually, it's hard to predict exactly what kind of warnings SmartScreen will give you, because it uses some kind of reputation system, which is not very transparent (the main idea is that, the more users install and approve Thonny, the more likely it is that next users won't be bothered with warnings).

How to work around SmartScreen Filter?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
* Option 1: If you run Thonny installer from Internet Explorer or Edge and see the warning "SmartScreen Filter reported Thonny-1.0.6.exe as unsafe", then click the button "View downloads", right-click on thonny installer and select "Run anyway". (We would be really glad, if you later also clicked "Report that this download is safe" -- this would add to Thonny's reputation and would reduce Windows' alarm level about Thonny)
* Option 2: Just download the installer, open your Downloads folder in Windows Explorer and run the installer from there. Most likely you will see the usual confirmation titled "Do you want to run this file?". Just click "Run" and the installer will start.
* * If you get something stronger (eg. warning with no option to confirm your intention, or request to provide admin password when you don't have one), then close the warning, right-click the installer, select "Properties" and check "Unblock" at the bottom of "General" tab. Click "OK" and after this you should be able to run installer without problems.