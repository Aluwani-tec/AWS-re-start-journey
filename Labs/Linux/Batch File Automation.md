# Linux Command Line and Shell Scripting Labs

This document captures multiple Linux labs completed in the same working environment.  
The labs focus on text processing, automation, and backup scripting using standard Linux tools.

---

# Lab 1: Linux File Processing and Text Manipulation

## Lab Objective
To create and process structured text files using Linux command-line utilities.

## Lab Overview
This lab focused on working with CSV-style data files. The tasks simulated real-world scenarios such as listing data, sorting records, searching for values, extracting columns, and transforming file formats directly from the terminal.

## Steps Taken
1. Confirmed the working directory before creating or modifying files.
2. Listed existing files to verify the environment state.
3. Created CSV files using input redirection.
4. Sorted file contents alphabetically.
5. Searched for specific values within files.
6. Extracted specific columns using delimiters.
7. Modified file content using in-place editing.
8. Verified outputs after each operation.

## Commands Used and Purpose
- `pwd` — confirm the current working directory.
- `ls` — list files (e.g., used to list datasets such as provinces or cities).
- `cat > filename.csv` — create CSV files and enter data manually.
- `sort filename.csv` — organize records alphabetically.
- `grep <value> filename.csv` — search for specific entries in the file.
- `cut -d ',' -f1 filename.csv` — extract the first column using a comma delimiter.
- `sed -i 's/,/./' filename.csv` — replace delimiters to transform file formatting.
- `cat filename.csv` — verify final file content.

## Outcomes
- Files were created and processed successfully.
- Data was filtered, sorted, and transformed correctly.
- Outputs matched expected results after verification.

## Challenges
- Minor command typos caused execution errors.
- Delimiter handling required careful attention when extracting fields.
- In-place editing required validation to avoid unwanted changes.

## Lessons Learned
- Linux text-processing tools are powerful and efficient.
- Command accuracy is critical.
- Always verify output after transforming files.

---

# Lab 2: Linux Batch File Automation Using Shell Scripts

## Lab Objective
To automate repetitive file creation using a Bash script with state tracking.

## Lab Overview
This lab demonstrated how shell scripts can be used to generate multiple files automatically while maintaining continuity between executions using a state file.

## Steps Taken
1. Created a dedicated working directory for automation.
2. Created a state file to store the next starting number.
3. Wrote a shell script to generate files in sequential order.
4. Assigned execution permissions to the script.
5. Executed the script multiple times to confirm it continued from the correct point.
6. Listed files to verify successful automation.

## Commands Used and Purpose
- `mkdir` - create a directory for automation tasks.
- `cd` - move into the working directory.
- `echo <number> > .nextnum` - store the starting number for automation.
- `cat .nextnum` - verify the stored state value.
- `nano make_batch.sh` - create and edit the automation script.
- `chmod +x make_batch.sh` - allow script execution.
- `./make_batch.sh` - run the script.
- `ls` - confirm generated files exist.

## Outcomes
- Files were created automatically in sequence.
- Script executions did not overwrite previous files.
- State tracking worked as expected.

## Challenges
- Forgetting execution permissions prevented script execution.
- Incorrect logic could lead to duplicate file creation.

## Lessons Learned
- Automation saves time and reduces human error.
- State persistence is essential for repeatable scripts.
- Scripts should always be tested more than once.

---

# Lab 3: Linux Backup and Archiving Automation

## Lab Objective
To automate directory backups using shell scripting and compressed archives.

## Lab Overview
This lab focused on creating a reusable backup script that archives a directory into a timestamped `.tar.gz` file and stores it in a dedicated backup location.

## Steps Taken
1. Created a backup script file.
2. Updated file permissions to allow execution.
3. Used `tar` with compression to archive a directory.
4. Generated timestamped backup filenames.
5. Verified backup creation by listing the backup directory.

## Commands Used and Purpose
- `touch backup.sh` - create the backup script.
- `chmod 755 backup.sh` - enable script execution.
- `./backup.sh` - run the backup script.
- `tar` - archive and compress files.
- `date` - generate timestamps for backup names.
- `ls backups/` - verify backup files exist.

## Outcomes
- Backup archives were created successfully.
- Files were compressed and stored correctly.
- Timestamping improved traceability.

## Challenges
- Using incorrect `tar` flags caused failed backups.
- Incorrect paths resulted in incomplete archives.

## Lessons Learned
- Backup automation improves reliability.
- Verification is as important as backup creation.
- Compression reduces storage usage and improves portability.

---

## Evidence (Shared Across All Linux Labs)

The following screenshots demonstrate command execution, scripting, automation, and verification across all three labs:

### Linux Command Execution and Text Processing
![Linux Evidence 1](https://github.com/Aluwani-tec/AWS-re-start-journey/blob/main/Labs/Linux/images/aws.linux.PNG?raw=true)

### Backup Script Execution and Archive Verification
![Linux Evidence 2](https://github.com/Aluwani-tec/AWS-re-start-journey/blob/main/Labs/Linux/images/aws.linux2.PNG?raw=true)

### Batch Automation and Script-Based File Creation
![Linux Evidence 3](https://github.com/Aluwani-tec/AWS-re-start-journey/blob/main/Labs/Linux/images/aws.linux3.PNG?raw=true)
