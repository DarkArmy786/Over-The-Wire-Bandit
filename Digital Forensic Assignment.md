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









