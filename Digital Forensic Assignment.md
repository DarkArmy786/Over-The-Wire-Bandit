# Over-The-Wire-Bandit ( Level 1-10 )
This repository contains a step-by-step guide for solving levels 0 through 10 of the Bandit wargame from OverTheWire. Each level includes commands, explanations, and tips to help beginners understand Linux basics and cybersecurity principles.


# Bandit Level 0 → Level 1
ssh bandit0@bandit.labs.overthewire.org -p 2220

Key Takeaways: learn how to log into a server using SSH from a command-line terminal.
The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game. 



File: readme

Password for Level 1: ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If

![image](https://github.com/user-attachments/assets/3494c7ee-1db2-413f-9d8c-dd7874c5ac61)

![image](https://github.com/user-attachments/assets/aca1c942-ad7e-4f1c-b751-f405a028817b)


# Bandit Level 1 → Level 2
ssh bandit1@bandit.labs.overthewire.org -p 2220

Password for Level 1: ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If


Key Takeaways: learn how to read files with special characters, which is "-" in this case.
The - is not treated as a filename. In Unix/Linux commands, a single dash - usually means:
“Read from standard input (keyboard) instead of a file.”
So cat - waits for you to type something instead of reading a file.

When the file is literally named -, you need to tell Linux:
"Don't treat this as an option or stdin, treat it as a file."

So you use:
cat ./-
./ means: “in the current directory”

"-" is now treated as a filename, not an option

The password for the next level is stored in a file called - located in the home directory.


File: -

Password for Level 2: 263JGJPfgU6LtdEvgfWU1XP5yac29mFx

![image](https://github.com/user-attachments/assets/b4386e01-40cf-41b8-a36e-f51cdbca80cd)

![image](https://github.com/user-attachments/assets/42283942-5259-4dcc-9e71-3846c9f1b068)


# Bandit Level 2 → Level 3
ssh bandit2@bandit.labs.overthewire.org -p 2220

Password for Level 2: 263JGJPfgU6LtdEvgfWU1XP5yac29mFx

Key Takeaways: learn how to read files with spaces in its file name.
The password for the next level is stored in a file called spaces in this filename located in the home directory.


Command: cat spaces\ in\ this\ filename
Alternatives: cat "spaces in this filename"
File: spaces in this filename
Password for Level 3: MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx

![image](https://github.com/user-attachments/assets/21b273cf-c186-423c-91bf-8bedff308445)

![image](https://github.com/user-attachments/assets/8a978dd4-4562-4147-894d-69635dea52b7)


# Bandit Level 3 → Level 4
ssh bandit3@bandit.labs.overthewire.org -p 2220

Password for Level 3: MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx

Key Takeaways: learn how to see all files in a directory, by using the -a (--all) argument to the ls command.
The password for the next level is stored in a hidden file in the inhere directory.

File: ...Hiding-From-You

Password for Level 4: 2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ

![image](https://github.com/user-attachments/assets/0ad30b83-d701-41aa-82e4-72fcf3d25f8d)

![image](https://github.com/user-attachments/assets/3748f357-2ad8-4659-8063-a2f86a0f7523)


# Bandit Level 4 → Level 5
ssh bandit4@bandit.labs.overthewire.org -p 2220

Password for Level 4: 2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ

Key Takeaways: learn how to discover the type of a file, by using the file command.
The password for the next level is stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.

Command: file ./-file*
Note: human-readable file means a file with only ASCII text in this context.

File: -file07

Password for Level 5: 4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw

![image](https://github.com/user-attachments/assets/fd47ce7f-ce76-4372-a4a0-d153201d9029)

![image](https://github.com/user-attachments/assets/d865fce0-0be6-4292-a11e-23d8c94f57ca)


# Bandit Level 5 → Level 6

ssh bandit5@bandit.labs.overthewire.org -p 2220

Password for Level 5: 4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw

Key Takeaways: learn how to find a targeted file given a set of properties, by using the find command.
The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties: human-readable
1033 bytes in size
not executable

Command: find -type f -readable ! -executable -size 1033c
Alternative: find -size 1033c (go straight for the most distinguishing property out of all the ones listed; this works in this context only because there was only 1 file which was 1033 bytes in size)
Note: suffix 'c' is found after 1033 to specify the units to be bytes. The command will not work if no units were stated.
Note: optional to include a '.' (dot) after the find command and before specifying the type, to indicate that all directories and files are being searched.
Additional practice: learn how to find files of size greater than or less than a given size.

File: maybehere07/.file2
Password for Level 6: HWasnPhtq9AVKe0dmk45nxy20cvUa6EG


![image](https://github.com/user-attachments/assets/57e067fe-19ef-42fe-90f5-7d95f92d3ccd)


# Bandit Level 6 → Level 7

ssh bandit6@bandit.labs.overthewire.org -p 2220

Password for Level 6: HWasnPhtq9AVKe0dmk45nxy20cvUa6EG

Key Takeaways: learn how to find a targeted file given a set of properties, by using the find command (similar to previous one, except with a different set of search criteria).
The password for the next level is stored somewhere on the server and has all of the following properties: owned by user bandit7
owned by group bandit6
33 bytes in size

Note: Since it is stated that the password is stored somewhere on the server, we must first navigate to the root folder. cd .. twice from the home directory, and then pwd to verify that we are in the root directory. We should only see the slash ('/') character from running pwd.
Command: find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
Note: There are a lot of files which match the given property, but all of these files (except one) cannot be accessed, as seen from the string of "Permission denied" messages displayed. Only one search result does not have this message.
File: ./var/lib/dpkg/info/bandit7.password
Password for Level 7: morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj

![image](https://github.com/user-attachments/assets/8590792d-6cb9-424a-866d-b43be8292f92)


# Bandit Level 7 → Level 8

ssh bandit7@bandit.labs.overthewire.org -p 2220
Password for Level 7: morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj


Key Takeaways: learn how to search for a specific word within a file, by using the grep command.
The password for the next level is stored in the file data.txt next to the word millionth.

Command: grep millionth data.txt
File: data.txt
Password for Level 8:dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc

![image](https://github.com/user-attachments/assets/a318795d-409e-4bf7-a0c3-8b8e530465f5)


# Bandit Level 8 → Level 9
ssh bandit8@bandit.labs.overthewire.org -p 2220
Password for Level 8:dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc

Key Takeaways: learn how to search within a file given a set of criteria, by using the sort and uniq commands, in addition to piping within the terminal.
The password for the next level is stored in the file data.txt and is the only line of text that occurs only once.

Command: cat data.txt | sort | uniq -u
Note: -u argument indicates to print only the unique lines.
File: data.txt
Password for Level 9: 4CKMh1JI91bUIZZPXDqGanal4xvAg0JM

![image](https://github.com/user-attachments/assets/b0d8bb1e-a7fb-4da9-8949-874313141675)


# Bandit Level 9 → Level 10

ssh bandit9@bandit.labs.overthewire.org -p 2220
Password for Level 9: 4CKMh1JI91bUIZZPXDqGanal4xvAg0JM

Key Takeaways: learn how to search for strings within a file that does not contain only ASCII characters, by using the strings and grep command.
The password for the next level is stored in the file data.txt in one of the few human-readable strings, beginning with several ‘=’ characters.

Note: file data.txt tells us that the file is a data file, and does not contain only ASCII text. Hence, it was mentioned that there are only a few human-readable strings.
Command: strings data.txt | grep ===
File: data.txt
Password for Level 10:FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey

![image](https://github.com/user-attachments/assets/3f6e115e-15cb-4cea-9fbc-722b4fd253b6)



# Bandit Level 10 → Level 11

ssh bandit10@bandit.labs.overthewire.org -p 2220
Password for Level 10:FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey

Key Takeaways: learn how to decode base64 encoded data, using the base64 command.
The password for the next level is stored in the file data.txt, which contains base64 encoded data.

Command: base64 -d data.txt
Note: -d argument indicates decoding of data.
File: data.txt
Password for Level 11:dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr 

![image](https://github.com/user-attachments/assets/53f25800-bb7f-478e-aa27-86e7b41add2d)







