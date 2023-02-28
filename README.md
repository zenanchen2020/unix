# unix
about some unix skills

Final Exercises
These exercises combine information that you have learned in previous lessons and contains even some new commands that you need to figure out from Google. To get started, first connect to your Ubuntu server on Azure first:

ssh yourUser@yourIp
Exercise 1
Create new user in your Ubuntu system called niceuser.
Check your /etc/passwd file and make sure that the user exists in there.
Exercise 2
Create directory imgs
Go to directory imgs
Download file https://github.com/samk-ai/cmd-tools-course-materials/blob/main/images/cars/audi.jpeg?raw=true as car.jpeg
Download file https://github.com/samk-ai/cmd-tools-course-materials/blob/main/images/nature/bridge.jpeg?raw=true as nature.jpeg
Go back one directory
Create archive niceimages.tar.gz from folder imgs.
Verify that the archive contains the correct files.
Exercise 3
View the contents of website https://www.google.com using these two commands:

curl
w3m (you need to install packages w3m and w3m-img), you can exit from the terminal browser using the q key.
Exercise 4
During the courses you have installed some software through package manager to your system. Now find the paths of those executables where they are in Path so you know where the package manager installed them:

python3
tree
apache2
w3m
Exercise 5
Autojump is a nice software for Unix systems that learns in what folders you have been and you can just type little bit of the folder and autojump will automatically jump into that folder, if you have already been in that folder.

Now, let's install autojump and set it up to work:

We need to first link python 3 as python to your /usr/bin folder, do that using this command: sudo ln -s /usr/bin/python3 /usr/bin/python
With Git, clone autojump git repository located at git://github.com/wting/autojump.git
Go to folder autojump
Run the install.py script using the python3 install.py command
The script tells you to add certain text to your .bashrc file, do that.
Reload your .bashrc file
Make sure that autojump is working by moving between some directories like /bin, ~/ and then using the j bin command.
Exercise 6
Using the ufw firewall command, do these (you need to Google around how to achieve these):

Open port 25
Open port 24
List your ufw rules to make sure that those ports are open
Close port 25
Close port 24
List your ufw rules to make sure that those ports are now closed.
Exercise 7
As Unix is known for multitasking, you can also view what processes you have running on your system. To start the process manager shipped with Ubuntu, run command htop.

Using the process manager, on topleft corner you can see your CPU, RAM and swap memory usage. Below you can see all the processes you have running. To close the process manager, press q.

Now, all the processes you saw running in the process manager are running in the background. It is very easy to run something in the background of your system. Let's try running something in the background and stopping it:

To run command in the background, end it with &. By default, the command will still print output of it to your console, you need to also redirect output of the command to empty device called /dev/null. Run this command to check how long it takes to connect to google.com every 10 seconds: ping -i 10 google.com &>/dev/null &
Run htop to view all processes
Press f3 to search and type: ping and press enter
Press f9 to kill the process and press enter to send sigterm for the process (signal terminate) which terminates the process
Press q to quit from process manager.
Exercise 8
Make your package manager (apt) to moo!

          (__)
          (oo)
    /------\/
   / |    ||
  *  /\---/\
     ~~   ~~
..."Have you mooed today?"...

Advanced Exercises
Think you are tough? Alright – let's play a game...

Some of these advanced exercises require you to input arguments for your shell scripts. Inside your shell script, arguments use this kind of naming scheme: $1, $2... For example if your script is named myscript and you call your script as myscript file.txt nicefolder/ $1 would contain <b>file.txt</b> and $2 would contain nicefolder/.

Advanced Exercise 1
This tar command takes ridiculous amount of arguments to work, we need to fix this Jesse. Jesse – let's fix this.

Create script tar_compress_gzip in your /usr/bin folder that accepts the folder to compress and archive name as arguments. This script then creates the archive using gzip compression.
Make sure that your script works.
Advanced Exercise 2
Same as Advanced exercise 1, but instead of compressing, this will extract the given archive (with extension) to given folder. Name your script as tar_extract_gzip. Make sure that your script works.

Advanced Exercise 3
Create script find_in_files in your /usr/bin folder that accepts one argument: text to search from files starting from current directory.
Make sure that your script works.
Advanced Exercise 4
Create script find_file in your /usr/bin folder that accepts two arguments: Folder where to search for (resursively) and file to search for.
Make sure that your script works.
Advanced Exercise 5
In the three scripts you have created in these advanced exercises, add argument check as the first thing in your script. You need to check that user inputs the required arguments and if not, echo to the user how your script needs to be executed.
Advanced Exercise 6
Run the ping (ping -i 10 google.com) command used in exercise 7 using screen instead of &. You will have to figure out how the screen works ;)
