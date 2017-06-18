## How to run Java using Sublime Text 3 on Mac OS

There are many solutions out there that kind of say the same thing without providing a step-by-step. So here was my experience on a Mac'16 with Sublime Text 3:

Open a terminal window and do the following:

$ cd /Applications/Sublime\ Text.app/Contents/MacOS/Packages/
Made a temp directory to mess with.

$ mkdir java
Copy current Java.sublime-package into new java directory and cd into java.

$ cp Java.sublime-package java/

$ cd java
Then, unzip the package to see the contents:

$ unzip Java.sublime-package
Now, edit the build file, JavaC.sublime-build. If you have sublime text's command line script:

$ subl JavaC.sublime-build
Otherwise,

$ vi JavaC.sublime-build
Then I copied the following into my JavaC.sublime-build which I found here posted by Sean Mullen:

{
    "cmd": ["javac \"$file_name\" && java \"$file_base_name\""],
    "shell": true,
    "file_regex": "^(...*?):([0-9]*):?([0-9]*)",
    "selector": "source.java"
}
After that, save, and while inside the java directory type:

$ zip Java.sublime-package *
Move new build package to necessary folder (parent directory):

$ mv Java.sublime-package ../
Remove temp java directory:

$ rm -fr java/
And DONE. Now building the Java file will now attempt to run it as well. I prefer this behavior instead of having to do another "variant" to run the program.
