# Linux Class Notes

> Comprehensive Linux training notes formatted for GitHub Markdown.


========================================================================Class -01 02-05-2026
========================================================================ttouch <file_name> -----> To create the file
touch f1
touch f2 f3 f4
clear ----> To clean the screen
========================================================================ls ----> To list the files
ls -l ---> To list the files and directories in long format (Alphabetical Order)
ls -lt --> List all the files and directories based on the time
ls -lrt -> List the files and directories in the reverse order
ls -lrth --> List the files and directories in the reverse order with the size
========================================================================mkdir <directory_name> ----> To create the directory
mkdir sagar
mkdir test test1 test2
cd <directory_name> ----> To get onto the directory
cd sagar
cd .. ---> To go one step back or go back to previous directory
cd ----> To go back to the home
========================================================================pwd ----> Present working directory
========================================================================rm <file_name> ----> To delete the file
rm f1
rm f2 f3 f4
rm -rf <directory_name> ----> To delete the directory
rm -rf sagar
rm -rf test test1

rm * -----> To delete all the files in pwd
rm -rf * --> To delete all the file and directories in the pwd
rm *.c ----> To delete all the files with extension .c
rm *.txt ---> To delete all the files with extension .txt
VI text editor

Vi <file_name> ----> To create the file and edit the file

i ----> Insert Mode

esc + :wq! -----> Save and Quit the file
esc + :w   -----> Save
esc + :q!  -----> Quit without saving


cat < file_name > ----> To display the content of the file

esc + u ---> undo
esc + :set nu ----> To set the line number in a file
esc + :set nonu ----> To remove the line number in a file
esc + :4        ----> It moves the cursor to the 4th line
find and replace in Vi editor

esc + :%s/<old_word>/<new_word>/ig -----> To find and replace the string
esc + :%s/linux/windows/ig

% ----> All the lines
s ----> substitute
g ----> globally
i ----> Case sensitive

esc + :%s/linux/windows/ig -----> To replace the string in all the lines
esc + :2s/linux/windows/ig -----> To replace the string in the 2nd line
esc + :2,3s/linux/windows/ig -----> To replace the string in the 2nd to 3rd line
esc + :2,$s/linux/windows/ig -----> To replace the string from 2nd line till end of the file
esc + :2s/linux/windows/ig | 5s/linux/windows/ig -----> To replace the string in 2nd and 5th line

esc + dd -------> To delete the whole line in a file
Print in linux

echo -----> To print in linux

ex:
echo "welcome to ss training"
output:
Welcome to ss training

ex:
echo -e "welcome \nss training"
output:
welcome
ss training
Assignment
Display the contents of the file in reverse order

# Class -02 03-05-2026

redirect (>) ----> used to write the output of a command to a file and if the file is not present , it will create the new file (replace the original content of the file)
echo "welcome" > <file_name>
echo "welcome" > test

append (>>) ------> it will write the output of a command at the end of the file and if the file is not present , it will create the file

echo "ss training" >> <file_name>
echo "ss traning" test

output:
welcome
ss training
COPY

cp <file_1> <file_2> -----> Copy the contents of file_1 to file_2 (acts as a redirect )
ex: cp test test1

cp <file> <directory> ----> To copy the files onto the directory
ex: cp test /home/ec2-user/demo1/test/

cp -R <dir_1> <dir_2> ----> To copy the data from dir_1 to dir_2
ex: cp -R test2 demo1
move (mv) ----> ( It is used to move the files/directories , as well as to rename the files or directories )

mv <file_1> <file_2> ------> Move the file from file_1 to file_2 (rename the file)
mv <file> <directory> -----> Move the file to the directory
mv <dir_1> <dir_2> -------> To move the directories from dir_1 to dir_2
Word Count

wc <file_name> ----> To check the number of lines, words and characters in a file
wc -l <file_name> ---> Prints only the number of lines in a file
wc -c <file_name> ---> Prints only the number of characters in a file
wc -w <file_name> ---> Prints only the number of words in a file


ex:
wc test
2 6 33 test
grep ----> It is used to search for a particular pattern/string in a file

grep <pattern> <file_name> ----> it will display all the lines with the pattern present
grep -w <pattern> <file_name> -> it will search only for the full strings not the sub-strings
grep -e <pattern1> -e <pattern2> -> it is used to search for multiple pattern in a file
grep <^pattern> <file_name> ----> It will print all the lines starts with the pattern
grep <pattern$> <file_name> ----> It will print all the lines ends with the pattern
grep -v <pattern> <file_name> ---> Prints all the lines without the pattern
grep -c <pattern> <file_name> ----> To count the number of lines , where the pattern is present
grep -i <pattern> <file_name> ----> incase of case sensitive
Permission for a file and directory

owner group other
-rw-  r--   r--.
 6    4     4

r ----> read ------> 2^2 ---> 4
w ----> Write -----> 2^1 ---> 2
x ----> execute ---> 2^0 ---> 1

chmod <permission> <file_name> ------------------> setting the permission of a file

chmod -R <permission> <directory_name> ------------------> setting the permission for a directory

chmod 777 <file_name>
chmod 644 <file_name>
chmod 555 <file_name>
chmod 700 <file_name>

chmod 777 <file_name> ----> we are setting the permission for a file, where owner group and others has got read write and execute permission
u ----> owner
g ----> group
o ----> others

chmod u+rwx <file_name> ----------> it adds read, write and execute permission to the owner
chmod ug+rwx <file_name> ---------> it addsd read,write and execute permission to the owner and group
chmod o-r <file_name> -------> it removes the read permission from others
chmod u-x <file_name> -------> it removes the execute permission from the owner

# Class -03 05-05-2026

umask ----> it is the default permission set to a file/directory in the Linux

default permission of a file and directory
file ---> 666
Directory ---> 777

umask 002

666   777   666
002   002   000
---   ---   ---
664   775   666

To set the umask value
umask <value>

ex: umask 000
666   777
000   000
---   ---
666   777

To make the changes permanently  ----> /etc/profile
sudo su -
vi /etc/profile
umask <value>
just restart the session (permanent change)
sudo ---> superuser do
it gives the permission for us or a user to execute the commands as a root user

sudo <command> ----> it will provide the root privileges  to the current user (ec2-user)
To switch to the root user ----> sudo su -
exit ---> To come out from the root/current user
users

sudo useradd <user_name> -----> To create the user
sudo useradd ss

sudo passwd <user_name> ----> To set the passwd
sudo passwd ss

sudo userdel <user_name> ---> To delete the user
sudo userdel ss

To list the users ------> getent passwd  or cat /etc/passswd

ss:x:1001:1001::/home/ss:/bin/bash
user:x:UID:GID::Home_directory:Shell
su - <user_name> ----> To switch to different user (-)  ---> it loads the user env and moves onto there home directory
su - ss
To provide the user sudo permission, we need to add the user in the sudoers file

vi /etc/sudoers

<user_name> ALL=(ALL) NOPASSWD: ALL
ss          ALL=(ALL) NOPASSWD: ALL  ----> user
%training   ALL=(ALL) NOPASSWD: ALL  ----> group
To enable password authentication in the server
1. Be a root user ----> sudo su -
2. vi /etc/ssh/sshd_config
3. make passwordauthentication yes
4. systemctl restart sshd
Groups:

sudo groupadd <group_name> -----> To create the group
sudo groupadd training

sudo groupdel <group_name> ----> To delete the group
sudo groupdel training

To list all the groups ----> getent group or cat /etc/group

Note: When the user is created, automatically the group also gets created
When the user is deleted, the group can also be deleted, provided no other users belong to it.

To add an user to the group  ----> usermod -aG <group_name> <user_name>

example: To add ss user to the training group
sudo usermod -aG training ss
training ----> group
ss       ----> user
ownership

-rw-r--r--. 1 ec2-user ec2-user   0   Jun 21  03:10  f1
Permission    user     group     size date    time  file/directory

chown <user_name> <file/directory>  -----> To change the user/owner of a file/directory
chown ss f1

chgrp <group_name> <file/directory> -----> To change the group of a file/directory
chgrp training f1

To change the owner and group for the file/directory
chown -R <user_name>:<group_name> <file/directory>
chown -R ss:training f4
Linux Architecture

hardware ----> Kernal -----> Shell -----> Application ----> User

Hardware ----> CPU,RAM and storage

Kernel -----> It is the core part of the linux, which is responsible for all the major activities. it interacts directly with the underlaying hardware

Note: if kernel goes down, we cannot perform any operations in the ec2 machine ( we cannot connect to the ec2 itself)

Shell -----> it is the interface between user and kernel , it takes the command from the user and execute in the kernel function

example: free -h
who ----> To check all the users who has logged onto the system
whoami ---> To check the current user
hostname ---> To check the private DNS
hostname -s ---> To get only the private Ip
curl ifconfig.me ---> To check the public ip
uname ----> To check the operating system
uname -a ---> To check all the details of the operating system
uname -r ---> To check the kernel version of operating system
free -h ----> To check the ram usage
df -h -----> To check the disk usage
nproc ----> To check the number of CPU allocated for the system
du -sh <file/directory> ----> To check the size of a file or a directory
Assignment:
1. Command to list the volume block
2. What is stickybit
3. Create the user and user should be able to perform the sudo permission (install git)
4. check the history of users logged in and who was the last logged in user
5. extend the current user password for 30days
6. How do you change the user password ?

# Class -04 06-05-2026

head ----> To print the required number of lines of a file

head <file_name> ----> by default , it will display the starting 10 lines
head -n <file_name> ----> it will display starting n lines
ex: head -5 <file_name> ----> it will display first 5 lines
tail ----> To print the last lines of file

tail <file_name> ---> by default it displays the last 10 lines
tail -n <file_name> ---> it displays the last n lines
ex: tail -5 <file_name> --> it displays the last 5 lines
Pipe [ | ] ----> To pass the output of a command as input of the next command

example:
To print 7th and 8th line in file
head -8 <file_name> | tail -2

search for a ss user
getent passwd | grep ss

search for the training group
getent group | grep training

search for particular file
ls -l | grep <file_name>
sed ----> stream editor, used to find the and replace, delete and also to print the lines

sed 's/<old_word>/<new_word>/ig' <file_name> ----> it will replace the oldword with newword in all the lines and displays the output on the terminal

-i ----> represents the permanent change ( when we use -i, it does not display the output on the terminal)

sed -i  '1s/<old_word>/<new_word>/ig' ----> it will apply the changes on the first line
sed -i  '1,3s/<old_word>/<new_word>/ig' ----> it will apply the changes from 1st to 3rd line
sed -i  '2,$s/<old_word>/<new_word>/ig' ----> it will apply the changes from 2nd end of the file line
sed -i  '2s/<old_word>/<new_word>/ig; 5s/<old_word>/<new_word>/ig' ----> it will apply the changes on 2nd and 5th line

sed -i '2d' <file_name> ----> it will delete the 2nd line
sed -i '2,$d' <file_name> ---> it will delete the lines from 2nd to end of the file
sed -i -e '2d' -e '5d' <file_name> ----> it will delete 2nd and 5th line of a file
sed -i '2,4d' <file_name> ---> it will delete the lines from 2nd to 4th line of the file

sed -n '5p' <file_name> ----> To print 5th line of a file
sed -n '2,5p' <file_name> ----> To print lines from 2nd to 5th line
sed -n '2,$p' <file_name> ----> To print lines from 2nd to end of the file
sed -n  -e '3p' -e '5p' <file_name> ----> To print 3rd and 5th line
cut ---> cut command is used to cut the file column wise

cut -d " " -f1 <file_name> ------> It will cut the first column

-d ---> delimiter
" " --> separator

Note: We cannot have the multiple separator/function in cut

ex:1
si name section subject
1  abc   A      Maths
2  def   B      English
3  xyz   C      Science
4  mno   D      Social

cut -d " " -f1,3 <file_name> ----> it will cut the 1st and 3rd column
cut -d " " -f1-3 <file_name> ----> it will cut 1st to 3rd column

ex2:
si-name-section-subject

cut -d "-" -f1 <file_name> ----> it will cut the first column in a file

echo "si-name-section-subject" | cut -d "-" -f1
awk ---> It is used to cut the file column wise ,row wise and where the multiple functions are available

-F ----> Field Value

awk -F " " '{print$1}' <file_name> -----> it will cut the first column
awk -F " " '{print$2}' <file_name> -----> it will cut the second column
awk -F " " '{print$2,$3}' <file_name> -----> it will cut the 2nd and 3rd column
awk -F " " '{print$2,$3,$5}' <file_name> -----> it will cut the 2nd,3rd and 5th  column
awk -F " " '{print$NF}' <file_name> -----> it will cut the last column
awk -F " " '{print$(NF-1)}' <file_name> -----> it will cut the last 2nd column

awk '{print}' <file_name> ----> To print the contents of the file , its an alternative command for the cat

awk 'NR==2' <file_name> ----> it will display or cut the 2nd row
awk 'NR==2 || NR==3' <file_name> ---> it will display the 2nd and 3rd row
awk 'NR==2 || NR==3 || NR==5' <file_name> ---> it will display the 2nd,3rdand 5th row
awk 'NR>1' <file_name> ----> It will cut/display all the rows after 1st
awk 'NR>1 && NR<4' <file_name> ---> It will cut/display all the rows between 1st and 4th
tree ----> The tree command is used to check the directory structure
sudo yum install tree
yum ----> installation package manager for amazon linux machine
apt ----> installation package manager for ubuntu machine
find ----> To find the files and directories in a linux (Recursive)

./ ----> Home Path (/home/ec2-user)

-type f ----> To find the files
-type d ----> To find the directories

find -type f -name <file_name> ----> it will search for the file
find -type f -name f1

find -type d -name <directory_name> ----> it will search for the directory
find -type d -name demo1

find -mtime -5 ----> To find all the files/directories that are created in last 5 days
find -type f -mtime -5
find -mtime +5 ----> To find all the files/directories that are created more then 5 days
find -type d -mtime +5

find -type f -name "*.c" ----> it will list all the files with the extension .c

find -type f -name "*.txt" ----> it will list all the files with the extension .txt

find -type f -empty -----> it will display all the empty files

find -type f -perm 777 ----> it will list all the files with permission 777
Assignment:
Find all the non-empty files
find the files with the size more than 1MB
find and delete all the empty files (pipe command)

# Class -05 07-05-2026

Links ----> To create the shortcut of a file

Softlinks:
ln -s <original_path_of_the_file> <softlink_name> ----> it will create the softlink of the file in PWD

A softlink will point towards the path  of the file, once the original file gets deleted/removed the softlink will not work

Hardlink:
ln <original_path_of_the_file> <hardlink_name> ----> it will create the hardlink of the file in PWD

Hardlink will point towards the inode of the file,  so even if original file gets deleted, the hardlink still works
Both orginalfile and Hardlink will share the same inode number

inode: Inode is an unique identification number given to a file, which points towards the memory block
ls -i <file_name/Hardlink_name>
To transfer the data from local system to the remote server or remote server to the local system we can use winscp or filezilla
The protocol used here is SFTP (secure file transfer protocol) (22)
SSH ----> Secure Shell or secure socket shell, it is the network protocol that gives users/administrators to secure way to access the computer/server


Protocol       Port
SSH            22
SFTP           22
FTP            21
HTTP           80
HTTPS          443

Application
Jenkins       8080
tomcat        8080

Port -----> A port is a Virtual Access Point, where the network connection start and end, Each port is associated with Particular service or process

passwordbased
ssh -i <path_to_pem_key> username@hostname
ssh -i DevOps-May-2026.pem ec2-user@172.31.46.77

chmod 400 <pem_key>
<path_to_pem_key> ----> This is the keypair/pem_key of the Secondary Server
username -------------> Username of the secondary Server
hostname -------------> Private or Public if of the secondary Server
SSH Passwordless

ssh-keygen -t rsa ----> it is used to generate the rsa key (public and private key), with which we can set up the passwordless connection

ls -a ----> It is used list all files/folder including the hidden files/directories
ls -d .* ---> To list only the hidden files/directories

now in .ssh folder, copy the contents of id.rsa.pub file from the primary server to the authorized_keys of the secondary server, which is located in the .ssh folder


ssh <username>@<hostname>
ssh ec2-user@172.31.46.77

username -------------> Username of the secondary Server
hostname -------------> Private or Public IP of the secondary Server

exit  -----> To exit from the secondary server
SCP (secure copy) ----> It is used to copy the files/directories from the primary server to secondary server

with password
scp -i <path_to_pem_key> <file/directory> username@hostname:<destination path of the secondary server>

ex:
scp -i DevOps-May-2026.pem demo ec2-user@172.31.46.77:/home/ec2-user

Without Password:
scp <file/directory> username@hostname:<destination path of the secondary server>
scp DevOps-May-2026.pem ec2-user@172.31.46.77:/home/ec2-user

rsync ----> we can also use rsync to copy the files/directories from one server to the anather server , but the major difference with scp is, in rsync, if there is any failure in data transfer, the rsync will resume the copy process from where it got stopped

rsync -avz <file/directory> username@hostname:<destination path of the secondary server>
rsync -avz DevOps-May-2026.pem ec2-user@172.31.46.77:/home/ec2-user

a ---> Archive mode (preserves permission, timestamp etc.)
v ---> verbose mode
z ---> Compress data during data transfer

with PEM KEY
rsync -avz -e "ssh -i /path/to/key.pem" <file/directory> username@hostname:<destination path of the secondary server>

ping --->  ping is commonly used to check the reachability of a server

ping <hostname> ----> it is used to ping the anather server
ping 0 -----> it is used to ping the current server

ex:
ping www.google.com
Assignment:
1. Install tomcat on the amazon linux machine

  ----> hostmanager
  ----> managerapp
  ----> change the port to 8090

  ----> java
  ----> wget
  ----> unzip

sudo yum install java ----> To install java

# Class -06 08-05-2026

ps -ef -----> To list all the running process (sshd,systemd,cron)
ps -u <user_name> ----> it will show you all the process started by an user
sudo pkill -u <user_name> ---> To stop all the process started by an user


PID ---> Process ID

sudo yum install docker

Services:
gracefully
sudo systemctl status <service_name> ----> To check the status of the service
sudo systemctl start <service_name> ----> To start the service
sudo systemctl stop <service_name> ----> To stop the service
sudo systemctl restart <service_name> ----> To restart the service
sudo systemctl enable <service_name> ----> it automatically starts the service, when the server gets rebooted

or
sudo service <service_name> stop
sudo service <service_name> start
sudo service <service_name> restart
sudo service <service_name> status

sudo systemctl status docker
sudo systemctl start docker
sudo systemctl stop docker
sudo systemctl restart docker
sudo systemctl enable docker

Forcefully:
sudo systemctl kill <service_name>
sudo systemctl kill docker
systemctl kill -s KILL docker ----> Forcefully

Forcefully Process:
-9 ----> To forcefully kill the process

kill <PID> ----> To kill the process given by the PID (gracefully)
kill -9 <PID> ----> To kill the process given by the PID (forcefully)
kill -9 4525

killall -9 <process_name>. ----> To kill the process given by the process_name
killall -9 -u <user_name> -----> To kill all the processes started by an user
killall -9 -u ec2-user

top ----> To check all the running process,memory and cpu etc.

uptime ---> To check from how long the server is running and the load average
01:54:28 up 27 min,  1 user,  load average: 0.09, 0.04, 0.01
Load average: cpu consumption in last 1min, 5min and 15 min

q ----> To exit from the running process in linux
bashrc and bash_profile ----> These files get executed every time automatically when the session starts

bashrc and bash_profile are located in the hidden files ( ls -a )

bashrc ---> nonlogin shells
bash_profile ----> login shells

Login shell ---> First shell after logging into server using PuTTY.
Non-login shell ---> Shell opened inside an already logged-in session (like running bash or duplicate session/tab).

whenever you make some changes to the bashrc and bash_profile , the session needs to be restarted to affect the changes

we can also setup alias(shortcut) in bashrc/bash_profile for a command (these values you cannot use in programs)

alias FE="find -type f -empty"
alias RM="rm -rf *"

Environment variables
export FM="Welcome to the linux class" (temporary)
echo $FM
welcome to the linux class

To set the env varible permently
 vi /etc/environment
 MY_VAR="hello_world"

When you set the env variables in bashrc/bash_profile those are available to specific user only
uniq and sort

uniq <file_name> ----> To display the uniq values in a file

drawback with uniq command is , it will only remove the duplicate values, if they are adjecent to one anthor, to fix this issue we use sort and uniq commands together

sort <file_name> ----> Sort the values
sort -r <file_name> --> Reverse order

sort <file_name> | uniq
tee

ls -l | tee <file_name> ---> It is used to write the output of a command to file and it also display the output on the terminal

ls -l | tee -a <file_name>
netstat ----> To check the information about the ports in linux

sudo yum install net-tools

netstat -a -----> To list all the ports (connected,listening established)
netstat -l -----> To list all the listening ports
netstat -tulnp ---> To check which process using which port

TCP/UDP sockets use IP + port to identify endpoints.

UNIX domain sockets use a file path on the local filesystem instead.
Example: /run/docker.sock or /run/systemd/private

A LISTENING socket is waiting for incoming connections.
A CONNECTED socket is actively connected between two endpoints.
Established connection is active and ready for data transfer

& ----> Run the script/command in the background

syntax: commad/script &
ex: rsync -avz demo1 ec2-user@172.31.13.34:/home/ec2-user &

fg ----> To bring the command/script to the foreground
To view all the background jobs ---> jobs
to bring back to the foreground ----> fg %<job_id>
                                  ex: fg %1
timedatectl -------------------> To check the current timezone
timedatectl list-timezones ----> To list all the available timezones in the linux
timedatectl set-timezone Asia/Kolkata ----> example to set the timezone
date ----> To check the date and time
Assignment:
1. learn about telnet
2. Difference between bashrc and bashprofile
3. learn about screen command
screen
screen -ls
screen -r <screen_name>
CTRL AD
4. How do we rollback in linux
5. How to check the inode usage and inode issues in linux
6. Learn about booting sequence in linux
7. What is zombie process
8. how do we block particular ip in Linux
9. what is IP table and how to block the IP adress
history ----> To check the commands given to the linux
bash_history ---> it will store all the commands given to linux from the day of launching the server




