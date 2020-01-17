# *nix Scavenger Hunt

Complete the following challenges using the command-line interface on your favorite
Unix or Linux operating system. You are welcome and encouraged to consult any
additional documentation online or in books.

Please add your answers/responses/text pastes to the document after each prompt.

Note: For some of the challenges you will need to reference files included with
this repository, so you will need to fork the repo into your own Github account
and then clone it to your development environment.

## The Challenges

### Navigating the Filesystem

* Get an idea of where you are in the operating system. Use the `pwd` command to find your "path to working directory"--your current location in the filesystem of your devbox. *Paste the output of the `pwd` command here: /Users/jasonbanks

* Discover more about this filesystem. Use `ls` (the "list" command)to see what is in this directory. *What directories and files do you see when you run `ls`?Applications
Creative Cloud Files
Desktop
Documents
Downloads
Dropbox
Library
Movies
Music
Pictures
Public
jason@harrismoure.com Creative Cloud Files
projects
temp

* You can use *options* to modify how a command runs. Try using `ls -alh` to see the contents of your current directory. *How are the results different when you use the `-alh` options? Detailed information is provided like whether an item is a directory or not, the user, security access level, size, date modified...*

* The `man` ("manual") command tells you more about how any given command works. (*WARNING:* CodeAnywhere does not support the man command. You can click the following link to complete this task: http://man.he.net/). Run `man` to see instructions about how to use `man`. Then use `man` to learn what the `a`, `l`, and `h` options mean when used with the `ls` command. *'man' provides access to manual pages
'ls -a' Include directory entries whose names begin with a dot (.)
'ls -l' (The numeric digit ''one''.) Force output to be one entry per line. This is the default when the output is not to a terminal.
'ls -h' When used with the -l option, use unit suffixes: Byte, Kilobyte, Megabyte, Gigabyte, Terabyte and Petabyte in order to reduce the number of digits to three or less using base 2 for sizes.

* Commands can also take *arguments*, which are usually the names of files or locations that you want the command to work with. Try running `ls /` to see what files are in the *root* directory of the filesystem. *Applications	
etc
Library			home
Network			installer.failurerequests
System			net
Users			private
Volumes			sbin
bin				tmp
cores			usr
dev				var

* A Unix filesystem has a few special shortcuts to refer to specific locations. `/` indicates the *root* of the filesystem, meaning the top-most directory in the filesystem hierarchy. Use the `cd` ("change directory") command to move to the root directory. (Hint: Use `man` to look up the `cd` command if you have any issues) *Then run `pwd` and paste the output here: /

* Another special shortcut in Unix is the `~` location. This indicates the *user root* directory, meaning the top-most directory in the hierarchy that comes below your user account. Use `cd` to move to `~`. /Users/jasonbanks

* Change directory into the `challenge_files` directory. Use `ls` to find only the files with a `.demo` pattern. *How many files do you find?*
27

* Use the `cd` command to move "up" one directory. *Where are you in the filesystem now?*
/Users/jasonbanks/projects/wats1030-intro-to-unix

* Press the up arrow on your keyboard. *What just happened?*The prior command that I just used came up

* Press the up arrow a few more times. *What do you see?*
All prior commands appear

* Run the `history` command. *What do you see?*
Looks like a history of all the commands that I have used
### Observing the System

* Discover what account you are logged into using the `whoami` command. *What username are you currently using?*
jasonbanks

* Discover who else is on your system with the `who` command. *Are any other users using your system? If so, list them here:*
just me, no intruders lol

* How long has your system been running? Use `uptime` to see, and *paste the result here:*
7 days, 23 hours...time for a shutdown

* Run `ps aux` and review the results. (Hint: Use `man` to learn more about the `ps` command and options.) *How do you interpret what you see here?*
Current applications installed on computer

* Run `top` and review the results. (Hint: You may need to use `ctrl-c` to get out of this app.) *How do you interpret what you see here?*
Current applications that are running. Like accessing the task manager on a PC

### Finding and Viewing Files

* Make sure you are in the `challenge_files` directory. Use the `*` wildcard to find all the files that have the word "credit" in the filename. *How many files did you find?*
Two

* Use the `more` command to view one of the `credit_cards` files you just discovered. (Hint: Type `q` to quit viewing the file. Press the `spacebar` to page down. Use your keyboard arrows to move up/down.) *What is the date in the file you have viewed?*
01.15.2015

* Use the `find` command to search for files more effectively. Search the sub-directories under `challenge_files` to find the location of the file named `modi_laboriosam.txt`. *Where is that file located?*
./tmp/modi_laboriosam.txt

* Use the `grep` command to search for text within a file. Use `grep` on all the `.user` files in `challenge_files` to find which files contain "WA" (the abbreviation for Washington state). *How many files did you find?*
Two

* Use the `-r` option of `grep` to *recursively* find the text "Waldo" hidden in a file somewhere under the `challenge_files` directory. *Paste the result showing the file and line where the word "Waldo" shows up.*
serial-numbers/eaque_molestiae.txt:Ut est maiores quia autem. Nisi modi Waldo sed corporis sit explicabo ut est. Et est placeat ea sunt sunt consectetur sunt incidunt. Explicabo vel esse blanditiis dolorem culpa non quia.

### Pipes and Connecting Commands

* Sometimes it's useful to output the results of a command to a text file for further analysis, reference, or processing. Try running `ls > files.txt`. Notice that the file `files.txt` was created. View that file using `more`. *What do you see in the `files.txt` file?*
The file names of everything in the challenge_files directory

* Notice that if you run `ls -alh` in the `challenge_files` directory, the files scroll by very quickly. Sometimes it would be better to get the results in a paginated format. Try running `ls -alh | more`. *Describe what you see when you run `ls -alh | more`.*
It allows you to scroll through the files pressing enter, shows the first set of files in a directory as opposed to all

* Earlier, when you viewed the list of active processes on your devbox using `ps aux`, the list was probably really long. You can make this list more manageable by using the pipe (`|`) to filter the results of `ps` using `grep`. Run `ps aux | grep <your_username>` to see what processes are running for your specific user. *Paste the list of processes that reference your username here:*
Selection of processes:
jasonbanks         313   0.0  0.2  4339004  12764   ??  S     8Jan20   0:04.25 /usr/libexec/pkd
jasonbanks         302   0.0  0.1  4342764   8320   ??  S     8Jan20   0:03.07 /usr/libexec/lsd
jasonbanks         290   0.0  0.0  4308736   3216   ??  S     8Jan20   0:12.64 /usr/sbin/cfprefsd agent
jasonbanks         288   0.0  0.1  4331652   9268   ??  S     8Jan20   0:00.15 /System/Library/Frameworks/LocalAuthentication.framework/Support/coreauthd
jasonbanks        7951   0.0  0.0        0      0   ??  Z    Mon01PM   0:00.00 (Acrobat Update H)
jasonbanks       12200   0.0  0.0  4268040    792 s000  S+    7:19PM   0:00.00 grep jasonbanks
jasonbanks       12197   0.0  0.2  4333012  16332   ??  S     7:18PM   0:00.12 /System/Library/PrivateFrameworks/AOSKit.framework/Versions/A/XPCServices/com.apple.iCloudHelper.xpc/Contents/MacOS/com.apple.iCloudHelper
jasonbanks       12150   0.0  0.3  4329944  28804   ??  S     7:16PM   0:00.07 /System/Library/Frameworks/CoreServices.framework/Frameworks/Metadata.framework/Versions/A/Support/mdworker_shared -s mdworker -c MDSImporterWorker -m com.apple.mdworker.shared
jasonbanks       12033   0.0  0.2  4843080  15160   ??  Ss    7:12PM   0:00.16 /System/Library/Frameworks/Metal.framework/Versions/A/XPCServices/MTLCompilerService.xpc/Contents/MacOS/MTLCompilerService
jasonbanks       12032   0.0  0.6  4964924  46820   ??  S     7:12PM   0:01.47 /Applications/TextEdit.app/Contents/MacOS/TextEdit
