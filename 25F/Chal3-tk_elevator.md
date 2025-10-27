# Challenge 3 - tk-elevator

**Date:** 2025-10-13 <br>
**Category:** misc

Each task/level involves steps to locate the login credentials for the next task. This writeup will list the steps needed to get the credentials. The next task can be moved to using `su --login level{x}_{id}`.

There are two flags in this challenge, note will be made when a flag is accesible from a task.

## Task 0
```bash
ls
cat creds_level1/creds_level1.txt
```

## Task 1
This level contains a large directory structure with the creds file being ... somewhere in there. Use grep to recusrivley search for the file.
```
grep -r creds ./  # Recursivley search for a file containing "level2", which is next levels username
cat {file_path}  # Copy the filepath that grep detected and cat the full file
```

## Task 2
This level contains a creds file bloated with lorem ipsum. Use grep to isolate the username and password.
```bash
grep level3 creds_level3.txt && grep password creds_level3.txt
```

## Task 3
This task has a bash scrip with the next level creds stored as a base64 encoded string within. You can manually decode the string using a varity of different tools, or just trigger the script to decode and print it for you using the following:
```bash
source ./creds_level4.sh
```

## Task 4
This task hides the credentials file using unix's . syntax.
```bash
cat .hidden_creds_level5/.creds_level5.txt
```

## Task 5
The first flag is accessible from this task.
```bash
cat /flag_1.txt
```

The task attempts to obfuscate the flag using special characters in the name, making tab autocomplete fail, however you can just type the full path out and access the file.
```bash
cat 'look in here'/'creds in here!'
```

## Task 6
This task presents us with a simple server thats been started with the credentials for the next task being provided as parameters for the process. To view the running 'server' and its credentials, we can use top.
```bash
top -U level6_44146 -c  # use the U flag to select down to our specific user and c to show the full command used to run each process
```

## Task 7
Exit Vim: `:q <enter>`

## Task 8
This task contains a git repo and a hint that the password is somewhere in the repo, we will use git's log to show the password.
```bash
cd project
git log
```

## Task 9
The computer "crashed" while writing the creds file and left a binary file behind. Read is and extract the plaintext password.
```bash
ls -la
cat .creds_level10.txt.swp
```

## Task 10
The second flag is accedible now: `cat /flag_2.txt`
