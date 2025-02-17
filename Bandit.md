### Task 1:
# Over the wire
## Bandit level 0
Hint :log into the game using SSH (secure shell)

### Tools and techniques used:
  * Used SSH to log in into the server

### Learning outcome:
 * ssh:  it is a command used to  secure connection b/w two devices 

Flag:

level 0:ssh bandit0@bandit.labs.overthewire.org -p2220

Password given : bandit0

resources used :

[ssh]( https://www.youtube.com/watch?v=Ei3nU-fHI6E)

[install and enable ssh]( https://www.youtube.com/watch?v=F1_fkOYgu8g)

[install and enable ssh](https://www.youtube.com/watch?v=Wlmne44M6fQ)


![bandit 0](<bandit level 0 b.png>)


## Bandit level 0 to level1
Hint : open the file called readme in the home directory

### Tools and techniques used:
*  cat : concatenate
* ls : list 



                                
### Learning outcome:
* cat: to open, display  files
* ls:  list all the files in the directory

Flag:

level 1: ssh bandit1@bandit.labs.overthewire.org -p2220

Password found for next level : ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If

![bandit 1](<bandit level 1.png>)

## Bandit level 1 to level 2

Hint  :open the file called “-” 
### Tools and techniques used:
* Used command like cat <  :to open files

                                                            
### Learning outcome:
 * "cat filename":
 directly open the file  and display its contents.
* "cat < filename":
 Used for input redirection : Redirect the files content to cat and display it 

* When the filename starts with a - (a dash), using the cat command directly could cause issues because it might be interpreted as an option instead of a filename

Flag:

level 2:ssh bandit2@bandit.labs.overthewire.org -p2220

Password found for next level: 263JGJPfgU6LtdEvgfWU1XP5yac29mFx

![bandit 2](<bandit level 2.png>)



## Bandit level 2 to level 3
Hint : open the file called spaces to get the password for next level 


                                                            
Learning outcome:
* ```Spaces in this filename``` is the file name so used ” ” 
* Found an alternative way:”\” after each word : "space\ in\t his\ filename
* By using a backslash before a space , you're telling the system to treat the     space  as part of the 
name rather than as a  special symbol.

* Flag:
level 3: ssh bandit3@bandit.labs.overthewire.org -p2220
Password found for next level: MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx


![bandit 3](<bandit level 3.png>)



## Bandit level 3 to level 4
Hint : open the hidden file  to get the password for next level 

### Tools and techniques used:
* Used command like ls -a 
### Learning outcome:
* ls -a is used to list out all hidden files 

Flag:

level 3: ssh bandit3@bandit.labs.overthewire.org -p2220

Password found for next level: MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx


![bandit 4 ](<bandit level 4.png>)

## Bandit level 4 to level 5
Hint : password stored in human readable file in inhere directory

### Tools and techniques used:
* Used command like 
* ls -a: list all files                                     
* cat <: to open files  which starts with -    
* cd to change direcotry                                       
### Learning outcome:
* Changed directory to inhere and listed out all the hidden files using ls -a thenopen the hidden file using cat command
                            
Flag:

level 4: ssh bandit4@bandit.labs.overthewire.org -p2220

password:2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ

![bandit 5 ](<bandit level 5.png>)



## Bandit level 5 to level 6
Hint : have to open a file with
* human-readable
* 1033 bytes in size
* not executable 
:These properties.

### Tools and techniques used:
* Used command like cat < : to open files
* file : used to find the type of file in the  direcort              
### Learning outcome:
* Changed directory to inhere and listed out all the files using “ls” then searched (find)for * a file which is readable(.-readable) ,
with a file size of  1033 bytes(-size 1033c) ```find . -readable -size 1033c ```

Here ```.``` used to look into files 

     ```\`` used to look into folders and files
     
Flag:

level5:ssh bandit5@bandit.labs.overthewire.org -p2220

password:HWasnPhtq9AVKe0dmk45nxy20cvUa6EG

![bandit 6](<bandit level 6.png>)


## Bandit level 6 to level 7
Hint : have to open a file with
 * owned by user bandit7
* owned by group bandit6
* 33 bytes in size

:These properties.
### Tools and techniques used:

* Used command like``` ~ ```to change into root directory
( Rest was same things)                                                            
### Learning outcome:
* Changed directory to root directory(~) and listed out all the files using “ls” then         searched (find)for a file with a file size of  33 bytes(-size 33c)  
From the list open the file “/var/lib/dpkg/info/bandit7.password” using cat command                                
                            
Flag:

level7: ssh bandit7@bandit.labs.overthewire.org -p2220

password:morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj

![bandit 7](<bandit level 7.png>)

## Bandit level 7 to level 8
Hint  :have to open data.txt
### Tools and techniques used:

Used command like ```grep``` :Global regular expression print 
                                                            
### Learning outcome:

  Grep: it allows you to search for specific strings or patterns in files, and gives output matching the words or lines
                            
Flag:

level8: ssh bandit8@bandit.labs.overthewire.org -p2220

password:dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
![bandit 8](<bandit level 8.png>)



## Bandit level 8 to level 9
Hint :have to open data.txt

### Tools and techniques used:

Used command like ```uniq ```
                                                            
### Learning outcome:
 Uniq filters out the repeated lines in a file. 
uniq is the tool that helps to detect the adjacent duplicate lines and also deletes the duplicate lines. uniq filters out the adjacent matching lines from the input file

                              
Flag:

level9: ssh bandit9@bandit.labs.overthewire.org -p2220

password: 4CKMh1JI91bUIZZPXDqGanal4xvAg0JM

![bandit 9](<bandit level 9.png>)
## Bandit level 9 to level 10
* Hint  :have to open data.txt
* human - readable string
* Preceded by several =

### Tools and techniques used:

Used command like ```grep``` for mentioning “ ====”
                                                            

                               
Flag:

level10: ssh bandit10@bandit.labs.overthewire.org -p2220

password: FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey

![bandit 10](<bandit level 10.png>)

## Bandit level 10 to level 11
Hint :have to open data.txt, Base64 encoded data

### Tools and techniques used:
pipe ``` | ```
                                                            
### Learning outcome:
*  pipe command | in Linux takes the output of one command and sends it as input to another command
  
* ```cat data.txt | base64  – decode ``` is used to decode the encoded data in base64
                              
Flag:

level11: ssh bandit11@bandit.labs.overthewire.org -p2220

password:dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr

![bandit 11](<bandit level 11.png>)
## Bandit level 11 to level 12
Hint  :have to open data.txt
 All uppercase and lowercase is rotated by 13 position

### Tools and techniques used:

Used the command : tr  :translate
                                                      
### Learning outcome:
* Learned about ROT 13 : letters in the messages is replaced with  the letter that comes 13 places after it in the alphabet.
*  tr [:lower:] [:upper:]  
  tr command in Unix/Linux, which translates or deletes characters. It can be used to perform a variety of transformations, including uppercase to lowercase, deleting specific characters, and basic find and replace. 
                              
Flag:

level12: ssh bandit12@bandit.labs.overthewire.org -p2220

password:7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4

![bandit 12](<bandit level 12.png>)

## Bandit level 12 to level 13
Hint  :have to open data.txt
      * File is hexdump make
      * Make dictionary under /tmp
         
### Tools and techniques used:
Used the command : 
* mkdir 
* /tmp/
* Xxd  
*  cp 
* mv : to move or rename
* gzip
* bzip2
* tar
* -xf 
                                                      
## Learning outcome:
* mkdir used to make directory   (make a temporary dir to work on )
* cp to change directory from one place to another
 (copy the data file to temporary dir )
* xxd to convert   hexdump back to original file 
* -r to revert the hexdump 
* Rename the file using mv  
* If it is gzip compressed data we  move the file from file name to filename.gz then decompress by  gzip -d filename.gz 
* If it is bzip2 compressed data ,convert the file to file.bz2 then use bzip2 -d filename.bz2 to decompress     
* tar -xf extract an archive to current direcotry   tar xf command is used to extractfiles from a .tar archive. It opens up the .tar file and puts all the files inside it into your current folder.

Flag:

level 13:ssh bandit13@bandit.labs.overthewire.org -p2220

password:FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn

![bandit 13](<bandit level 13 b.png>)

## Bandit level 13 to level 14
Hint  :have to open  /etc/bandit_pass/bandit14
* Need a private SSH key 
* ```localhost``` is the host name  
                                                                                       
### Learning outcome: 
``` ssh  -i sshkey.private -p 2220 bandit14@localhost ```( to log in into ssh private key)

Flag:

level14 :ssh bandit14@bandit.labs.overthewire.org -p2220

password: MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS

![bandit 14](<bandit level 14  a.png>)

## Bandit level 14 to level 15
Hint  :have to open  /etc/bandit_pass/bandit14
* Need a private SSH key 
* ```localhost``` is the host name  
* ```nc``` netcat
                                                                                       
### Learning outcome:
opened the file given in level 13 to 14 ``` /etc/bandit_pass/bandit14``` 
nd got the password

*netcat is where you can send and receive messages or files easily between computers.

Flag:


level15:ssh bandit15@bandit.labs.overthewire.org -p2220

password :8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo

![bandit 15](<bandit level 14 to 15.png>)

## Bandit level 15 to level 16
Hint  :   have to submit current password on localhost using SSL

 ssl : secure socket layer                            
### Learning outcome:
i used ssl to submit my current key on local host of port 30001
ssl is used to protect sensitive information , used to encrypt data between server adn client
* ```openssl s_client```
is a command  used for connecting to a server over SSL
* ```-connect <hostname>:<port>```

Flag:

level16:ssh bandit16@bandit.labs.overthewire.org -p2220

password got : kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx

![bandit 16 a](<bandit level 15 to 16 a.png>)

![bandit 16 b](<bandit level 15 to 16 b.png>)
