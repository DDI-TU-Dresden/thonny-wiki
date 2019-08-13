## Won't start and no error messages ##

If Thonny doesn't open and you don't see any error messages, then you have two options for going further -- either run it from the terminal and observe the messages printed there, or check the logs.

### Open in the Terminal (macOS) ###

First open the Terminal (under Utilities).

If you copied Thonny to your desktop then enter the following command:

```
~/Desktop/Thonny.app/Contents/MacOS/thonny
```
If it is under Applications, then use the following command instead:

```
/Applications/Thonny.app/Contents/MacOS/thonny
```

### See the logs (macOS) ###
The logs are in a hidden folder, so you can't just navigate there in Finder. You need to go there directly -- press `Command+Shift+G` and enter `~/Library/Thonny` into the dialog that appears. (If it complains that folder doesn't exist, then Thonny has probably crashed before creating this folder).

If you see any non-empty files with a ".log" extension, then you could inspect these to learn more (or send them to the Thonny developers).