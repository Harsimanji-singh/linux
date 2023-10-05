**Basic commands**

1. Pwd -> current directory
2. ls -> list the files
3. cd -> change directory (.. previous)
4. touch -> create file
5. mkdir -> create new directory
    mkdir -p=> path create 
6. sudo -> for root previlage
7. sudo touch file_at_root
8. rm -> delete the file
9. mv -> move file (mv file_path move_path)
10. mv -> for renaming mv file file1
11. rm -r -> remove folder
12. cat -> to read the file
13. whoami -> know the user
14. usermod -aG sudo user1 -> provide access to the sudo for user1 or be in group of sudo
    **Argument and options**
15. ls -l -> in listed manner with time and other things
16. ls -a -> show hidden folder
17. ls -la -> listed manner with hidden files
18. ls --help -> information for options
19. man (command) -> mannual for the commad
20. cal -y => full year calander
21. who => current user logins
22. tree => to shows the folder stucture
23. proc

**SUDO** -> provie access to root user

> ( run as administrator)

1. sudo -> for root excess
2. sudo visudo -> for changing settings
3. sudo -k -> logout the sudo session
4. sudo -i -> login to the root user
5. sudo passwd root -> change the password for the root user
6. sudo adduser username
7. su - username -> to change user

**vi text editor**

1. vi filename
2. i for inserting (before the character)
3. a for inserting(after the character)
4. o create a line and start writing
5. shift+o create line above
6. x -> deletes one characters
7. :wq -> saved changes and exit vi
8. :q! -> not saved and exit
9. /character -> to search the character and the cursor go to that
   and use "N" to next letter
10. shift+g -> last line
11. no. shift+g -> move to line no.
12. $ -> to go to the end of the line
13. 0 -> to begin the line
14. dw -> delete word
15. d^ -> delete before the cursor in fornt of line
16. d$ -> delete after to end
17. dd -> entire line
18. dG -> delete everything beneth the line
19. yy -> copy current line
20. p -> paste below the cursor

**not working backspace and arrowkeys in vi**
go to home directory
creat file using sudo vi .vimrc
put lin
set nocompatible
:wq to save

**Nano text editor**
simple text editor

1. ctrl+w -> search
2. alt+w -> next search word
3. ctrl+/ -> search the word write

**Users groups permission**

1. sudo cat etc/passwd => to get the user registered
2. sudo cat /etc/groups => to get the registed groups
3. getent groups => to get groups
4. vipw => if we need to make changes in /passwd file we need to use vipw as if we break something then it tweek you
5. groupadd name => create new groups
6. vigr => for groups like vipw
7. id -gn => provide primary group
8. userdel username => to delete user
9. passwd username => change password
10. usermod -aG doctors user1 => to add user to group
11. deluser => to remove user from the groups
    **permissions**
    ls -l => permission listed

    - rwx rwx rwx
      for - => file type "-" indicate file "d" indicate directory
      =>for 1st rw => read, write and execute permission to all user
      => for 2nd rwx => read , write, execute for group owner of file
      => read , write and execute permission for the file owner
      **method 1**

12. chmod u => change permission for user
13. chmod g => change permission for group
14. chmod o => change permission for others
15. chmod a => change permission for all of them - => give permission \* => take away the certain permission
    = => give exact permission
    chown newuser filename => change new user
    chgrp newgroup filename => change new group

    **compression and backups with gzip bizp and tar**

16. gzip filename => compression using gzip
17. gzip -d filename => decompress the file
18. gzip -c filename >> newname_compressed => compressed copy of the file
19. gzip -c -d filename_compressed >> newfile => decompress copied file
20. gunzip -c compressed_file | less => read compressed file
21. zcat compressedFile => read compressed file
22. gzip -9 filename => most compression but slow

**Redirects and pipes**
standardIN=> 0
standardOut => 1
standardError =>2

1.  echo 'some random text' 1> randomfile
    redirect the output to other file
    not shell
    default is out use only >

- both error and out in same file
  ./script.sh > combinedfile 2>&1
  it wipe the file and paste the output
  > > for append the data at the end
  > > pipe command used for append the output of one thing to input of the other thing

ls -l | less
ls -l | grep vdir
ls -l | wc -l => to count the no. of lines
ls -l | grep a | wc -l

**managing process**
control +z => suspend the process and get the job id
control + c => stop the process
fg <process no.> => start the process
for fg => command terminal stop
for bg => it run on the background

=> make the process in background
process at want + & sign => run in the background

zombie process => complete but still remain lack of coordintion b/w parent and child

1. ps => moniter process(user mode only by one user)
2. ps -U username => all process at user running at the moment
3. ps -aef => all different process
4. top => show the process in sort by cpu utilization defalult and any other

- sending signal to process(kill command)
  kill -l => show list of

1.  SIGHUP
2.  SIGINT
3.  SIGKILL => kill the process imedietly
4.  SIGTERM => kill the process gently as not corrupt the file only if not work send sigkill
5.  SIGSTOP =>

- kill sidId pid
- kill -9 pid => good way to kill the process

6. pgrep nameOfProces => give process id

niceness detemine the priority (-20 to 19) defalut 0 higher it means lower priority
ps -el => give niceness value
sudo nice --2 top => set priority of

- sudo renice -15 pId

**pacakeges**

1. dpkg -l => show all pacakeges
2. dpkg -s packagename => show specific pacakage
   .deb in linux(ubuntu) and .exe in window all pacakages installed in .deb extension
3. dpkg --print-architecture => show architecture
4. wget link => to download
5. dpkg --info packagename
6. dpkg -
# install the package
search ubuntu package 
first download the file with wget 
then install by dpkg -i with .deb file
search for architecture
7. wget provide the link  => wget used to download from website
dpkg --info 
8. sudo dpkg -i .deb file to install the package
**dpkg is not good method**

it is not used it not install the dependency with it 
use anotbher method

use apt => its package manager
1. apt-get/apt(new version) update => change the database that there is update version
use it as 
- sudo apt update && sudo apt upgrade -y => works for all the packages 
to remove the package
2. sudo dpkg -r package-name/ sudo dpkg -p 
P => remove the configuration file
r => keep the configuratoin file
3. search for package
repositories => cd /etc/apt
cat sources.list
apt-cache search htop => search the file
**install the package**
sudo apt-get update && sudo apt-get install nameOfThePackage (apache2)-y

pushd and popd => 
awk 
tr '[A-Z] '[a-z]'< cars


acls => permission

!*

man 2 stat
.bashrc file run while setting up the bash 
sort -o 
/dev/null
wc