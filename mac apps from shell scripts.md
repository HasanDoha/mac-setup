# Mac apps from shell scripts
Copy 'appify' file to a directory in your 'PATH' and name it appify (no extension).
I chose to put it in '/usr/local/bin', which requires root privileges.

Fire up Terminal.app and enter 
$ sudo chmod +x /usr/local/bin/appify
to make appify executable without root privileges.

After that, you can create apps based on any shell script simply by launching Terminal.app and entering something like this:
$ appify your-shell-script.sh "Your App Name"
Obviously, this would create a stand-alone application named Your App Name.app that executes the your-shell-script.sh script.

# Adding a custom app icon
Create an .icns file or a 512×512 PNG image with the icon you want, and copy it to the clipboard (⌘ + C). (Alternatively, copy it from an existing app as described in steps 2 and 3.)
Right-click the .app file of which you want to change the icon and select “Get Info” (or select the file and press ⌘ + I).
Select the app icon in the top left corner by clicking it once. It will get a subtle blue outline if you did it right.
Now hit ⌘ + V (paste) to overwrite the default icon with the new one.
Note that this will work for any file or folder, not just .app files.
