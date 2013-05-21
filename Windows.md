#Installing on Windows#

For Windows users, [msysgit](http://code.google.com/p/msysgit/) is a good
starting place for installing git.

##Cygwin##

For Windows users who wish to use the automated install, it is suggested that you install [Cygwin](http://www.cygwin.com/)
first to install tools like `git`, `util-linux` and `wget` (with those three being packages that can be selected
during installation). Then simply run this command from a Cygwin shell in your `$HOME`:

	$ wget -q -O - --no-check-certificate https://github.com/nvie/gitflow/raw/develop/contrib/gitflow-installer.sh | bash

If you get the error "flags: FATAL unable to determine getopt version" error after 

	$ git flow init

you need to install the `util-linux` package using the Cygwin setup.


##MSysGit##

Download and install `getopt.exe` from the [util-linux package](http://gnuwin32.sourceforge.net/packages/util-linux-ng.htm) into `C:\Program Files\Git\bin`. (Only `getopt.exe`, the others util-linux files are not used). Also install `libintl3.dll` from the [Dependencies package](http://gnuwin32.sourceforge.net/packages/libintl.htm), into the same directory. 

Clone the git-flow sources from GitHub:

	$ git clone --recursive git://github.com/nvie/gitflow.git
	$ cd gitflow

Run the `msysgit-install` script from a command-line prompt (you may have to
run it with "Full Administrator" rights if you installed msysgit with its
installer, and ensure you're running from a Windows command prompt, not MINGW):

	C:\gitflow> contrib\msysgit-install.cmd

In Git bash create a symbolic link for git-flow so that you can actually use the `$ git flow` command from any location.

	$ ln -s /C/gitflow/git-flow git-flow

##GitHub for Windows##

GitHub for Windows uses a portable installation of MSysGit for its shell. You'll need to follow the above instructions for MSysGit, except for two differences, both of which rely on the install location for GHfW's MSysGit install location. To find that location:

Navigate to the GitHub directory under the OS's "Local Application Data" directory. On Windows 7, it is located at: "C:\Users\USER_NAME\AppData\Local\GitHub".
Look for a directory named something similar to "PortableGit_8810fd5c2c79c73adcc73fd0825f3b32fdb816e7". Note: the GUID at the end may change.

Once you have the location, use it to perform the following (refer to the above MSysGet instructions above for more details):

Copy `getopt.exe` and `libintl3.dll` to the `bin` directory directly under the location found above. In Windows 7, you would copy the files to: `"C:\Users\USER_NAME\AppData\Local\GitHub\PortableGit_8810fd5c2c79c73adcc73fd0825f3b32fdb816e7\bin"`.

Open the GitHub for Windows Git Shell and check that you are in the GitHub root directory e.g. `C:\GitHub>`
Clone the GitFlow folder with 

	C:\GitHub> git clone --recursive git://github.com/nvie/gitflow.git

This will clone the GitFlow code into a new `gitflow` folder in your GitHub directory. You can select a different location if you prefer or you can remove the GitFlow clone later.

Change to the GitFlow directory:

	C:\GitHub> cd gitflow

Run the `msysgit-install` script with the location as a parameter. For example:

	C:\GitHub\gitflow [develop]> contrib\msysgit-install.cmd "C:\Users\USER_NAME\AppData\Local\GitHub\PortableGit_8810fd5c2c79c73adcc73fd0825f3b32fdb816e7"

Note: Replace `PortableGit_8810fd5c2c79c73adcc73fd0825f3b32fdb816e7` with the name of your directory; you do not need the \bin at the end.

Check that GitFlow is installed by calling the help:

	C:\GitHub> git flow help 
