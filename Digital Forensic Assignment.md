# Over-The-Wire-Bandit
This repository contains a step-by-step guide for solving levels 0 through 10 of the Bandit wargame from OverTheWire. Each level includes commands, explanations, and tips to help beginners understand Linux basics and cybersecurity principles.

Bandit Level 0 → Level 1
Key Takeaways: learn how to log into a server using SSH from a command-line terminal.
The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game. 

ssh bandit0@bandit.labs.overthewire.org -p 2220

File: readme
Password for Level 1: ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If

![image](https://github.com/user-attachments/assets/3494c7ee-1db2-413f-9d8c-dd7874c5ac61)

![image](https://github.com/user-attachments/assets/aca1c942-ad7e-4f1c-b751-f405a028817b)


Bandit Level 1 → Level 2
Key Takeaways: learn how to read files with special characters, which is "-" in this case.
The - is not treated as a filename. In Unix/Linux commands, a single dash - usually means:
“Read from standard input (keyboard) instead of a file.”
So cat - waits for you to type something instead of reading a file.

When the file is literally named -, you need to tell Linux:
"Don't treat this as an option or stdin, treat it as a file."

So you use:
cat ./-
./ means: “in the current directory”
- is now treated as a filename, not an option

The password for the next level is stored in a file called - located in the home directory.
ssh bandit1@bandit.labs.overthewire.org -p 2220

File: -
Password for Level 2: CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9

![image](https://github.com/user-attachments/assets/b4386e01-40cf-41b8-a36e-f51cdbca80cd)

