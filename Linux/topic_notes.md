# 🐧 Linux Module – AWS re/Start

This folder contains all Linux command-line practice completed during the AWS re/Start program. It includes file navigation, text processing, scripting, backups, and automation performed on Amazon Linux EC2 instances.

## 📘 Module Overview
This Linux module covers:
- Navigating the Linux filesystem  
- Managing files and directories  
- Using commands such as `pwd`, `ls`, `cat`, `sort`, `find`, `grep`, `cut`, and `sed`  
- Editing files using nano  
- Creating and executing shell scripts  
- Automating tasks using counters and loops  
- Compressing and archiving data  

## 🪪 Assignment 1 – Working With Files and CSV Data
**Screenshots:**  
`linux_csv_commands_1.png`, `linux_csv_commands_2.png`

**Tasks Completed:**
- Used `pwd`, `ls`, and `cat` to inspect files  
- Read CSV files (`test.csv`, `cities.csv`)  
- Sorted CSV data using `sort test.csv`  
- Searched for specific values using `find` + `grep`  
- Extracted columns with `cut -d ',' -f 1`  
- Replaced characters using `sed -i 's/,/./'`  

This exercise focused on basic Linux commands and working with text/CSV data.

## 🪪 Assignment 2 – Creating a Backup Script
**Screenshot:** `linux_backup_script.png`

**Tasks Completed:**
- Created a shell script (`backup.sh`)  
- Assigned executable permissions using `chmod 755 backup.sh`  
- Compressed directories using `tar`  
- Verified backups in the `backups/` folder  
- Reviewed output of archived files  

This assignment demonstrated automation and file archiving on Linux.

## 🪪 Assignment 3 – Batch File Generator (Automation)
**Screenshot:** `linux_batch_generator.png`

**Tasks Completed:**
- Created a batch directory  
- Used `.nextnum` file as a counter  
- Built a shell script (`make_batch.sh`) to:
  - Generate files with sequential numbering  
  - Track the next starting number  
  - Create batches of 25 files at a time  
- Learned how Linux scripts can automate repetitive tasks

## 🛠️ Key Skills Gained
- Navigating and managing directories  
- Editing and manipulating text files  
- Running and debugging shell scripts  
- Automating tasks using counters and loops  
- Processing CSV files from the command line  
- Creating compressed archives with `tar`  
- Using Amazon Linux EC2 for hands-on practice  

## 📝 Notes
All detailed Linux explanations and extended notes are stored in `topic_notes.md`.

## 📌 Status
✔️ CSV processing tasks completed  
✔️ Backup script completed  
✔️ Batch file generator completed  
✔️ Screenshots uploaded  
✔️ Notes updated

