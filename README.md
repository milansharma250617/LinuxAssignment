1. Create a directory named "MyFiles" in your home directory. Navigate into this directory and list its contents.

  milan@milan-Latitude-3340:~$ mkdir MyFiles
  milan@milan-Latitude-3340:~$cd MyFiles
  milan@milan-Latitude-3340:~$:~/MyFiles$ ls
  milan@milan-Latitude-3340:~$:~/MyFiles$


2.Copy a file named "document.txt" from your home directory to the "MyFiles" directory. Move the file to a subdirectory named "Documents" within "MyFiles."

  milan@milan-Latitude-3340:~$ touch doc.txt
  milan@milan-Latitude-3340:~$ cp doc.txt MyFiles/
  milan@milan-Latitude-3340:~$ cd MyFiles
  milan@milan-Latitude-3340:~$:~/MyFiles$ ls
  doc.txt
  milan@milan-Latitude-3340:~$:~/MyFiles$ mkdir Documents
  milan@milan-Latitude-3340:~$:~/MyFiles$ mv doc.txt Documents
  milan@milan-Latitude-3340:~$:~/MyFiles$ ls Documents
  doc.txt


3.Create an empty file named "notes.txt" in the "MyFiles" directory. Afterward, delete the file.

  milan@milan-Latitude-3340:~$:~/MyFiles$ touch notes.txt
  milan@milan-Latitude-3340:~$:~/MyFiles$ ls
  Documents  notes.txt
  milan@milan-Latitude-3340:~$:~/MyFiles$ rm notes.txt 
  milan@milan-Latitude-3340:~$:~/MyFiles$ ls
  Documents


4. Create a hard link named "hardlink.txt" for the file "document.txt" within the "Documents" subdirectory. Also, create a symbolic link named "symlink.txt" in the same location.

  milan@milan-Latitude-3340:~$:~/MyFiles$ cd Documents
  milan@milan-Latitude-3340:~$:~/MyFiles/Documents$ ls
  doc.txt
  milan@milan-Latitude-3340:~$:~/MyFiles/Documents$ ln doc.txt
  hardlink.txt
  milan@milan-Latitude-3340:~$:~/MyFiles/Documents$ ls
  doc.txt  hardlink.txt


5.In the "MyFiles" directory, use a single command to list all files that start with the letter "a" and have a ".txt" extension.

  milan@milan-Latitude-3340:~$:~/MyFiles$ ls ./a*.txt
  ls: cannot access './a*.txt': No such file or directory
  milan@milan-Latitude-3340:~$:~/MyFiles$ cd Documents
  milan@milan-Latitude-3340:~$:~/MyFiles/Documents$ ls ./a*.txt
  ls: cannot access './a*.txt': No such file or directory
  milan@milan-Latitude-3340:~$:~/MyFiles/Documents$ ls ./*.txt
  ./doc.txt  ./hardlink.txt

6.Rename all files in the "Documents" subdirectory of "MyFiles" with a ".bak" extension. Ensure the original file names are preserved.

  milan@milan-Latitude-3340:~$:~/MyFiles/Documents$ ls
  doc.txt  hardlink.txt
  milan@milan-Latitude-3340:~$:~/MyFiles/Documents$ sudo rename 's/   
  \.txt$/.bak/' *.txt
  milan@milan-Latitude-3340:~$:~/MyFiles/Documents$ ls
  doc.bak  hardlink.bak

7.Use a wildcard character to copy all files from the "Documents" subdirectory of "MyFiles" to another directory named "Backup."

  milan@milan-Latitude-3340:~$:~/MyFiles$ mkdir Backup
  milan@milan-Latitude-3340:~$:~/MyFiles$ ls
  Backup  Documents  hardlink.txt
  milan@milan-Latitude-3340:~$:~/MyFiles$ cp Documents/* Backup
  milan@milan-Latitude-3340:~$:~/MyFiles$ ls Backup
  doc.bak  hardlink.bak
  milan@milan-Latitude-3340:~$:~/MyFiles$ ls Documents
  doc.bak  hardlink.bak


8.Execute the ls command to list files in the current directory. Save the output to a file named "file_list.txt." Then, use a pipe to filter the output through grep to display only files with a ".txt" extension.

  milan@milan-Latitude-3340:~$ ls >file_list.txt
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

9.Create a new text file named "my_notes.txt" using the touch command. Open the file in the Vim editor, add some text, and save the changes.




10.Run the date command and store the output in a variable named "current_date." Display the value of the variable and append it to the "my_notes.txt" file.




11.Edit the Bash startup script (e.g., .bashrc) to set an environment variable named "CUSTOM_PATH" to a specific directory path. Ensure the variable is available in new shell sessions.





12.Use the echo command to add a new line of text to the "my_notes.txt" file without overwriting existing content. Verify that the new text is appended.

  milan@milan-Latitude-3340:~$ find ./my_notes*.txt
  ./my_notes.txt
   milan@milan-Latitude-3340:~$ cat my_notes.txt
   fosteringlinux
  milan@milan-Latitude-3340:~$echo KeenAble >>my_notes.txt 
  milan@milan-Latitude-3340:~$cat my_notes.txt 
  fosteringlinux
  KeenAble

13.List all files in the "/etc" directory, filter the output to include only those containing the word "conf," and save the result to a file named "conf_files.txt."

   milan@milan-Latitude-3340:~$ sudo find /etc -type f -name *conf* > 
   conf_files.txt
   milan@milan-Latitude-3340:~$ ls
   'All Gates.sim1'   doc.txt         my_notes.txt
   Arduino           Documents       Pictures
   Circuit.sim1      Downloads       Public
   Circuit.simu      file_list.txt   snap
   conf_files.txt    Music           Templates
   Desktop           MyFiles         Videos


14.Open the "my_notes.txt" file in Vim. Use Vim's search and replace functionality to replace all occurrences of the word "important" with "critical." Save the changes. 

   milan@milan-Latitude-3340:~$ vim my_notes.txt

   ![Alt text](<Screenshot from 2024-02-04 17-36-25-1.png>)

15.Create a new user account named "john_doe." Set the user's home directory to "/home/john_doe" and assign the user to the "users" group.

   milan@milan-Latitude-3340:~$ sudo useradd -m -d /home/john_doe 
   john_doe
   [sudo] password for ayan: 
   milan@milan-Latitude-3340:~$sudo passwd john_doe 
   New password:
   passwd: password updated successfully
   milan@milan-Latitude-3340:~$ sudo usermod -aG users john_doe 


16.Add the user "john_doe" to the sudoers file, allowing them superuser privileges. Confirm that "john_doe" can execute commands with sudo.

   milan@milan-Latitude-3340:~$sudo visudo
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


17. Modify the user account "john_doe" to change the default shell to "/bin/bash" and set the account's expiration date to one month from today.

   milan@milan-Latitude-3340:~$ sudo chsh -s /bin/bash john_doe 
   [sudo] password for ayan: 
   milan@milan-Latitude-3340:~$ sudo chage -E$(date -d '+1month' +%d-
   %m-%Y) john_doe 
   milan@milan-Latitude-3340:~$


18.Create a new group named "development_team." Add "john_doe" to this group and verify the group's existence.

   milan@milan-Latitude-3340:~$ sudo groupadd development_team
   milan@milan-Latitude-3340:~$ sudo usermod -aG development_team 
   john_doe 
   milan@milan-Latitude-3340:~$ grep development_team /etc/group
   development_team:x:1002:john_doe



19. Remove "john_doe" from the "users" group and add them to the "development_team" group. Confirm the changes.

   milan@milan-Latitude-3340:~$ sudo deluser john_doe users
   info: Removing user `john_doe' from group `users' ...
   milan@milan-Latitude-3340:~$ sudo usermod -aG development_team 
   john_doe 
   milan@milan-Latitude-3340:~$ groups john_doe 
   john_doe : john_doe development_team


20. Delete the user account "john_doe" and ensure that their home directory is also removed. 

    milan@milan-Latitude-3340:~$ sudo userdel -r john_doe 
    userdel: user john_doe is currently used by process 16134
    milan@milan-Latitude-3340:~$ ^C
    milan@milan-Latitude-3340:~$ sudo pkill -u john_doe
    milan@milan-Latitude-3340:~$ sudo kill -9 16134
    milan@milan-Latitude-3340:~$ sudo userdel -r john_doe 
    userdel: john_doe mail spool (/var/mail/john_doe) not found
    milan@milan-Latitude-3340:~$ ^C
    milan@milan-Latitude-3340:~$ ls /home/john_doe
    ls: cannot access '/home/john_doe': No such file or directory

21.Delete the group "development_team" and ensure that all users previously belonging to the group are appropriately handled.

   milan@milan-Latitude-3340:~$ grep development_team /etc/group
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


22.Implement a password policy that requires users to change their passwords every 90 days. Apply this policy to all existing and new user accounts.






23.Manually lock the user account "john_doe." Attempt to log in as "john_doe" to confirm that the account is locked. Then, unlock the account.





24.Use the id command to display detailed information about the "john_doe" user, including user ID, group ID, and supplementary groups.





25.Configure the password aging for the user "john_doe" to enforce a maximum password age of 60 days. Confirm that the changes take effect.







