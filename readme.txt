
Updating:

I periodically update the lftp binaries and dll files and push them into the repo.

# Troubleshooting:

ownership and deletion issues: double click on the "troubleshooting - ownership.bat" and accept with Y. Then delete the folder.

To fix files you cannot delete from the recycle bin run the "troubleshooting - ownership - recycle bin.bat" by right clicking and running as admin.

If you keep seeing that the lftp script is already running but you know it isn't, check the /tmp folder and delete the lock file then try again.

# Configuration

There is no conf/rc file with this set-up. You need to use an lftp scripts with your required options hardcoded and call that in ConEmu. It pretty much works out the same anyway.

# Directories:

The bin directory is home to most of the critical files. You don't really need to go in there, only to update the components.

Your lftp downloads will be saved to the Downloads directory, All included scripts are configured to do this.

To save elsewhere you must use full paths using the Cygwin directory method.

/cygdrive/c/download

Which translates into:

C:\downloads

Key - is where your private key will be stored. Not the ppk format - only openssh keys.

Scripts are stored in the scripts directory and this is where ConEmu will load itself by default.

tmp is just a temporary folder. you can mostly ignore this directory unless you need to remove the lock file.

# Files:

Most of the critical actions have been configured to run via double clicking some bat files. Here is a run-down of what they will do.

edit - connect.bysh.bat will open the included notepad ++ and the connect.bysh.lftp script for you to edit and save.

edit - connect.feral.bat will open the included notepad ++ and the connect.feral.lftp script for you to edit and save.

edit - connect.whatbox.bat will open the included notepad ++ and the connect.whatbox.lftp script for you to edit and save.

edit - connect.lftp.bat will open the included notepad ++ and the connect.lftp script for you to edit and save.

edit - lftpsync.sh.bat will open the included notepad ++ and the lftpsync script for you to edit and save.

Start - notepad - This will open notepad ++ in the main directory. This will allow you to open a file and be in the portable directory to begin with.

Start - ConEmu will open ConEmu in the script folder but not run or do anything.

Start - taskscheduler -  WIll open the windows taskscheduler

run - connect - Start a generic template script

run - connect.bysh.lftp will run the connect..bysh.lftp script and automatically minimise ConEmu to the task bar.

run - connect.feral.lftp will run the connect.feral.lftp script and automatically minimise ConEmu to the task bar.

run - connect.whatbox.lftp will run the connect.whatbox.lftp script and automatically minimise ConEmu to the task bar.

run - lftpsync.sh will run the lftpsync.sh script and automatically minimise ConEmu to the task bar.

Usage:

So the idea is this:

1: Configure and use the lftpsync script.

2: if you have not been provided a customised script by your host then run the edit - connect.lftp.bat and customise it to your details. The run the the runme.bat or runme - connect.lftp.bat

3: If you have been provided a custom script then simple run the relevant bat file if one was provided. If not, then use runme and load the script manually.