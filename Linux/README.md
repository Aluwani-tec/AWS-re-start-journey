# Linux Module 

This folder contains all Linux command-line practice completed during the AWS re/Start program. It includes file navigation, text processing, scripting, backups, automation, and hands-on EC2-based Linux exercises.

## Module Overview
The Linux module teaches core command-line skills required for cloud and system administration.  
Topics covered:
- Navigating the Linux filesystem  
- File and directory management  
- Viewing and processing text/CSV files  
- Using commands such as `pwd`, `ls`, `cat`, `sort`, `find`, `grep`, `cut`, and `sed`  
- Editing files with `nano`  
- Creating and executing shell scripts  
- Automating repetitive tasks  
- Archiving and compressing files using `tar`  

## 🪪 Assignment 1 – CSV File Processing (Command-Line Practice)
**Screenshots:**  
`linux_csv_commands_1.png`  
`linux_csv_commands_2.png`

**Tasks Completed:**
- Used `pwd`, `ls`, and `cat` to navigate directories and inspect files  
- Displayed CSV contents from `test.csv` and `cities.csv`  
- Sorted records using:  
  - `sort test.csv`  
- Searched for items using:  
  - `find | grep Paris test.csv`  
- Extracted specific columns using:  
  - `cut -d ',' -f 1 cities.csv`  
- Performed character replacement using `sed`:  
  - `sed -i 's/,/./' cities.csv`  

This assignment focused on real-world text processing and Linux command-line fluency.

## 🪪 Assignment 2 – Backup Script (Shell Scripting)
**Screenshot:** `linux_backup_script.png`

**Tasks Completed:**
- Created `backup.sh` to automate file archiving  
- Made the script executable using `chmod 755 backup.sh`  
- Compressed multiple directories using:  
  - `tar -czvf backup-CompanyA.tar.gz`  
- Verified that backups were stored in the `backups/` directory  
- Reviewed the archive content inside the compressed file  

This task demonstrated automation and the fundamentals of shell scripting.

## 🪪 Assignment 3 – Batch File Generator (Automation Script)
**Screenshot:** `linux_batch_generator.png`

**Tasks Completed:**
- Created a `batch-files/` directory  
- Added a `.nextnum` counter file to track numbering  
- Built `make_batch.sh` to automatically:
  - Generate 25 files per batch  
  - Name them sequentially (e.g., olivia21, olivia22 …)  
  - Update `.nextnum` to track next starting index  
- Executed the script multiple times to test repeat automation  

This highlighted how Linux scripts simplify repetitive tasks in system administration.

## Key Skills Gained
- Confident filesystem navigation  
- Linux file inspection & manipulation  
- CSV/text processing commands  
- Writing and running shell scripts  
- Automating tasks using loops and counters  
- Archiving and compressing files  
- Working with Linux inside an EC2 instance  

## Notes
Additional details and learning notes are stored in `topic_notes.md`.

## Status
 CSV processing completed  
 Backup script completed  
 Batch automation completed  
 Screenshots uploaded  
 Notes documented

