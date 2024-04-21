
Task 1:
 
To Navigate the file system using cd, ls, pwd, and mkdir commands.

- Created and connected to my AWS EC2 instance
- Created a folder or directory called "task1" and "inlinux" using the command mkdir task1; mkdir inlinux.
- used ls to check the content of the directory
- to go into into task1 directory, use the command cd task1
- To check which directory I was working in (my present working directory), I used the command pwd. 
- Used "mkdir foldername" to create a folder called navigation inside my task1 directory.
- To see the list of content of my task1 directory, I used ls command under the directory 

Task 2: 
To create and modify files using touch, nano, vim, and cat commands.
-  cd into the inlinux directory using the command line $ cd inlinux
- Used touch to create the 4 files using the command line $ touch "Bash" "sh" "Csh" "Ksh".
- used ls to see the content of the inlinux directory now have 4 new files in its folder
- added $ touch Linux to add an extra file to the directory.
- used the command line $ ls again to see changes have been made to the directory. 
 

Nano is a text editor in Linux and can be used to create files and also add and change the content of the file.
- Create file using command line $ nano file1. This opens the nano editor.
- entered my data into the file. Used ctrl+s to save and ctrl+x to exit
- Back to my syntax, I used command $ ls to see the new created file called file1. 
- to see the content (the data entered) of the new file I use $ cat file1.
⦁	[ec2-user@ip-172-31-94-205 ~]$ cat file1
⦁	Welcome to nano text editor
⦁	This is used to create and edit files in Linux.
⦁	
⦁	
⦁	Changes made can be saved using ctrl+s.

- Added more text to the file and checked the content of 
⦁	[ec2-user@ip-172-31-94-205 ~]$ cat file1
⦁	Welcome to nano text editor
⦁	This is used to create and edit files in Linux.
⦁	
⦁	
⦁	Changes made can be saved using ctrl+s.
⦁	
⦁	This changes can be edited and savesd again.
⦁	
⦁	$$$4$$$$$$44444
⦁	
⦁	And exited using ctrl+x.

 
-See the changes made reflected in your directory.
 

VIM as it is called vi improved is also used to create and modify text. 
- Used $ pwd to see if I am in my home directory
- Used the command $ vi bash1 to create a new folder
- New editor opens, press the I key to insert contents.
- Type to add contents and press Esc to end adding contents.
- Enter :wq! to quit, save changes and return to EC2 terminal.
- Use command line ls to list the content and see the new created folder "bash1" 
- Use cat to view the added contents and further changes made when the process is repeated.
 

Task 3: 
Managing users and groups using useradd, usermod, groupadd, and passwd commands. 
- To be able to create a user, I have to be a root user or be able to impersonate the root user.
- The command to do so is sudo. So the command line $ sudo chigo adds chigo as a root user.
- Use $ cat /etc/passwd to see the newly added user chigo.
 
Usermod is used to modify users and add them to the sudoer or wheel group.
- To add chigo to the sudoer group I used the command $ sudo usermod -aG wheel chigo.
- To see the content of the sudoer/ wheel group I use the command $ cat /etc/group. 
 
- To see that users have been added of the wheel group, I used the command $ cat /etc/group | grep wheel. we see the ec2-user and chigo.
 
- Using the ec2-user root user crendentials, I am able to use the following commands to to switch into chigo home directory and check if the credentials has received the rootuser / sudoer priveledged status
- $ cat /etc/sudoers | grep ec2-user.
- To switch Home directories from the ec2-user to chigo, I use $ su chigo .
- Enter my password
- Use $ cd .. to enter into  Chigo home directory.
- Use $ cd chigo and use $ sudo useradd chigo_pickin to create the user "chigo_pickin".  
 
- you can then see chigo is now able to added chigo_pickin as a root user.
 
groupadd is the command used, to create groups in Linux. For you to be to create or add groups, you need root user or sudoer file priviledges. It is worthy to note every file is owned by a user and a group.
-
 
-

- See at the bottom of the root users group
 

- Create groups using $ sudo groupadd Godwinners.

 
- At the bottom we see the new created group called "Godwinners".
 
-use $ cat /etc/group | grep Godwinners to see the group location and group id 1003.
 
- Added a user chigo to the group called Neche using the command "$ sudo groupadd Neche and then using the usermod command $ sudo usermod -aG to add user chigo into the group.
- I also deleted the group using the command $ sudo groupdel Neche or $sudo gpasswd -d chigo Neche.
 

Passwd has to do with user authentication and passwords for the instance
- At the begining, we have the ec2-user as the root user.
- $ sudo passwd chigo is the command line used to create or change the password
- New password is entered. Use the command line $ su chigo and enter the password to verify the new password worked.
- Password is authenticated, root user changes to chigo.
 

Task 4: Install software packages using package managers such as apt, yum, or dnf. 
Research the linux distribution that uses each package manager
Document how to install the packages use each
Package managers are used to install and run software packages in linux. They vary from linux distro to distro ( distribution).
Apt is a command that serves as a built-in installer in debian based systems and it is signified as a .deb file. It is used to download packages in debian and ubuntu systems.
- Go to the website and click on the software you want to download
- Chose the 64 bit .deb package and it will download the file
- Save the file to your local disk and open your terminal.
- Use the command $ cd downloads/ to go into your download folder. Use command $ ls to find and locate the file.
- Use the command $ sudo apt install ./filename to install the package. you will see the file name end in deb.
- It will ask for authentication, because you need priviledge crendentials to complete this task.
- Once you authenticate, it validates the software and looks for any dependencies and then install the package. 

Dnf is a major improved version of yum. The yum command $ ls -l /usr/bim yum will point to dnf-3
[ec2-user@ip-172-31-94-205 ~]$ ls -l /usr/bin/yum
lrwxrwxrwx. 1 root root 5 Feb 26 20:53 /usr/bin/yum -> dnf-3
It is a command built-in installer for RPM packages and it is signified as a .rpm file. It is used to download packages in Redhat, CantOS 8 and Fedora style systems. 
- Go to the website and click on the software you want to download
- Chose the 64 bit .rpm package and it will download the file either to the package installer or you want to save it to your local machine.
- Save the file to your local disk and drop to your terminal.
- Use the command $ cd downloads/ to go into your download folder. Use command $ ls to find and locate the file.
- Use the command $ sudo dnf install ./filename to install the package. you will see the file name end in rpm.
- It will ask for to authentication and once you authenticate, it will install the package like it did when using the debian systems.

YUM (Yellowdog Updater Modified) is an interactive, rpm based, package manager used in Fedora or CentOS 8 based systems like AWS. 
- It can perform sys update automatically, dependency analysis and obselete process based on repository metadata
- Install and remove packages and perform queries on installed or available packages.
- Chose the 64 bit .rpm package and it will download the file either to the package installer or you want to save it to your local machine.
- Save the file to your local disk and drop to your terminal.
- Use the command $ cd downloads/ to go into your download folder. Use command $ ls to find and locate the file.
- Use the command $ sudo yum install ./filename to install the package. you will see the file name end in rpm.
- It will ask for to authentication and once you authenticate, it will install the package like it did when using the debian systems.

DNF used to install a package called htop in my EC2 Instance. I go to my instance terminal and simply.
- Search for htop using the command $ dnf search htop and ran $ htop ,it shows a there is currently no package like htop nor is there a command like htop in the system.
- I enter the command $ sudo dnf install htop to install the package.
 

It ask if I am ok with the download and installation size. I enter Y for yes and it went ahead and installed the package. 
 

- I run htop again using the command $ htop and this time he gave me the output needed
 

Task 5: Monitor system resources using commands like top, ps, df, and free
These command are used to monitor and analyze the system resources of our Linux system.
TOP
- Type the top command to view real time system resource usage including CPU, Memory and process information.
 

PS 
- Type the command ps and the system displays a list of running processes and their status, including their process ID (PID), memory usage and CPU usage
 

DF
- Typed df -h to display a human readable format to examine disk space usage for each mounted filesystem.
 

FREE
- Displays information about the system's memory usage, including total used and available memory. Use the command $ free -h
 



 













' 
 
 
