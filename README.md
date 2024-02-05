1.milan@milan-Latitude-3340:~$ mkdir MyFiles
  milan@milan-Latitude-3340:~$cd MyFiles
  milan@milan-Latitude-3340:~$:~/MyFiles$ ls
  milan@milan-Latitude-3340:~$:~/MyFiles$


2.milan@milan-Latitude-3340:~$ touch doc.txt
  milan@milan-Latitude-3340:~$ cp doc.txt MyFiles/
  milan@milan-Latitude-3340:~$ cd MyFiles
  milan@milan-Latitude-3340:~$:~/MyFiles$ ls
  doc.txt
  milan@milan-Latitude-3340:~$:~/MyFiles$ mkdir Documents
  milan@milan-Latitude-3340:~$:~/MyFiles$ mv doc.txt Documents
  milan@milan-Latitude-3340:~$:~/MyFiles$ ls Documents
  doc.txt


3.milan@milan-Latitude-3340:~$:~/MyFiles$ touch notes.txt
  milan@milan-Latitude-3340:~$:~/MyFiles$ ls
  Documents  notes.txt
  milan@milan-Latitude-3340:~$:~/MyFiles$ rm notes.txt 
  milan@milan-Latitude-3340:~$:~/MyFiles$ ls
  Documents


4.milan@milan-Latitude-3340:~$:~/MyFiles$ cd Documents
  milan@milan-Latitude-3340:~$:~/MyFiles/Documents$ ls
  doc.txt
  milan@milan-Latitude-3340:~$:~/MyFiles/Documents$ ln doc.txt
  hardlink.txt
  milan@milan-Latitude-3340:~$:~/MyFiles/Documents$ ls
  doc.txt  hardlink.txt


5.milan@milan-Latitude-3340:~$:~/MyFiles$ ls ./a*.txt
  ls: cannot access './a*.txt': No such file or directory
  milan@milan-Latitude-3340:~$:~/MyFiles$ cd Documents
  milan@milan-Latitude-3340:~$:~/MyFiles/Documents$ ls ./a*.txt
  ls: cannot access './a*.txt': No such file or directory
  milan@milan-Latitude-3340:~$:~/MyFiles/Documents$ ls ./*.txt
  ./doc.txt  ./hardlink.txt

6.milan@milan-Latitude-3340:~$:~/MyFiles/Documents$ ls
  doc.txt  hardlink.txt
  milan@milan-Latitude-3340:~$:~/MyFiles/Documents$ sudo rename 's/   
  \.txt$/.bak/' *.txt
  milan@milan-Latitude-3340:~$:~/MyFiles/Documents$ ls
  doc.bak  hardlink.bak

7.milan@milan-Latitude-3340:~$:~/MyFiles$ mkdir Backup
  milan@milan-Latitude-3340:~$:~/MyFiles$ ls
  Backup  Documents  hardlink.txt
  milan@milan-Latitude-3340:~$:~/MyFiles$ cp Documents/* Backup
  milan@milan-Latitude-3340:~$:~/MyFiles$ ls Backup
  doc.bak  hardlink.bak
  milan@milan-Latitude-3340:~$:~/MyFiles$ ls Documents
  doc.bak  hardlink.bak


8.milan@milan-Latitude-3340:~$ ls >file_list.txt
  milan@milan-Latitude-3340:~$ ls
  'All Gates.sim1'   mpv-shot0001.jpg
  Arduino           Music
  Circuit.sim1      MyFiles
  Circuit.simu      Pictures
  Desktop           Public
  doc.txt           snap
  Documents         Templates
  Downloads         Videos
  file_list.txt
  milan@milan-Latitude-3340:~$ cat file_list.txt | grep '\.txt$'
  doc.txt
  file_list.txt


12.milan@milan-Latitude-3340:~$ find ./my_notes*.txt
  ./my_notes.txt
   milan@milan-Latitude-3340:~$ cat my_notes.txt
   fosteringlinux
  milan@milan-Latitude-3340:~$echo KeenAble >>my_notes.txt 
  milan@milan-Latitude-3340:~$cat my_notes.txt 
  fosteringlinux
  KeenAble

13.milan@milan-Latitude-3340:~$ sudo find /etc -type f -name *conf* > 
   conf_files.txt
   milan@milan-Latitude-3340:~$ ls
   'All Gates.sim1'   doc.txt         my_notes.txt
   Arduino           Documents       Pictures
   Circuit.sim1      Downloads       Public
   Circuit.simu      file_list.txt   snap
   conf_files.txt    Music           Templates
   Desktop           MyFiles         Videos


14.milan@milan-Latitude-3340:~$ vim my_notes.txt

   ![Alt text](<Screenshot from 2024-02-04 17-36-25-1.png>)

15.milan@milan-Latitude-3340:~$ sudo useradd -m -d /home/john_doe 
   john_doe
   [sudo] password for ayan: 
   milan@milan-Latitude-3340:~$sudo passwd john_doe 
   New password:
   passwd: password updated successfully
   milan@milan-Latitude-3340:~$ sudo usermod -aG users john_doe 


16.milan@milan-Latitude-3340:~$sudo visudo
   milan@milan-Latitude-3340:~$ sudo echo "Hello, I have sudo 
   privileges!"
   Hello, I have sudo privileges!
   milan@milan-Latitude-3340:~$ su - john_doe 
   Password: 
   su: Authentication failure
   milan@milan-Latitude-3340:~$ su - john_doe 
   Password: 
   $ apt update
   Reading package lists... Done


17.milan@milan-Latitude-3340:~$ sudo chsh -s /bin/bash john_doe 
   [sudo] password for ayan: 
   milan@milan-Latitude-3340:~$ sudo chage -E$(date -d '+1month' +%d-
   %m-%Y) john_doe 
   milan@milan-Latitude-3340:~$


18.milan@milan-Latitude-3340:~$ sudo groupadd development_team
   milan@milan-Latitude-3340:~$ sudo usermod -aG development_team 
   john_doe 
   milan@milan-Latitude-3340:~$ grep development_team /etc/group
   development_team:x:1002:john_doe



19.milan@milan-Latitude-3340:~$ sudo deluser john_doe users
   info: Removing user `john_doe' from group `users' ...
  milan@milan-Latitude-3340:~$ sudo usermod -aG development_team 
  john_doe 
   milan@milan-Latitude-3340:~$ groups john_doe 
   john_doe : john_doe development_team


20. milan@milan-Latitude-3340:~$ sudo userdel -r john_doe 
    userdel: user john_doe is currently used by process 16134
    milan@milan-Latitude-3340:~$ ^C
    milan@milan-Latitude-3340:~$ sudo pkill -u john_doe
    milan@milan-Latitude-3340:~$ sudo kill -9 16134
    milan@milan-Latitude-3340:~$ sudo userdel -r john_doe 
    userdel: john_doe mail spool (/var/mail/john_doe) not found
    milan@milan-Latitude-3340:~$ ^C
    milan@milan-Latitude-3340:~$ ls /home/john_doe
    ls: cannot access '/home/john_doe': No such file or directory

21.milan@milan-Latitude-3340:~$ grep development_team /etc/group
   development_team:x:1002:
   milan@milan-Latitude-3340:~$ sudo deluser 1002 development_team
   [sudo] password for ayan: 
   fatal: The user `1002' does not exist.
   milan@milan-Latitude-3340:~$ sudo gpasswd -d 1002 development_team 
   Removing user 1002 from group development_team
   gpasswd: user '1002' is not a member of 'development_team'
   milan@milan-Latitude-3340:~$ sudo groupdel development_team 
   milan@milan-Latitude-3340:~$ grep development_team /etc/gr
   groff/  group   group-  grub.d/ 
   milan@milan-Latitude-3340:~$ grep development_team /etc/group
   milan@milan-Latitude-3340:~$


22.






































