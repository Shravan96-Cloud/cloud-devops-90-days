# Day 2 — Linux Filesystem Navigation and File Management

## Objective

Practise navigating Linux directories, inspecting files, searching for files, and safely managing temporary files.

## Commands Practised

| Command | Purpose |
|---|---|
| `pwd` | Display the current working directory |
| `cd .` | Stay in the current directory |
| `cd ..` | Move to the parent directory |
| `ls -a` | Display hidden files and directories |
| `head -n 3 file` | Display the first three lines |
| `tail -n 3 file` | Display the last three lines |
| `less file` | View a file interactively |
| `find path -name "*.log"` | Find files matching a name pattern |
| `find path -type f` | Find files only |
| `find path -type d` | Find directories only |
| `rm -i file` | Request confirmation before deleting a file |
| `rmdir folder` | Remove an empty directory |
| `rm -r folder` | Remove a directory and its contents recursively |
| `cp source destination` | Copy a file |

## Log File Practice

Created a sample server log containing application startup, configuration, database, warning, and backup messages.

Used `head` to inspect the beginning of the log and `tail` to inspect its latest entries.

Used `less` to practise interactive file viewing.

## File Search Practice

Used `find` to locate files by name, search for `.conf` and `.log` files, and distinguish files from directories.

## Safe Deletion Practice

Created a temporary file, inspected it, removed it using interactive confirmation, and removed its empty parent directory.

## Final Practical Exercise

Created an application directory containing configuration, log, and backup directories. Generated sample logs, searched for files, inspected log contents, and copied a log file into the backup directory.

## Key Learning

Linux filesystem commands help administrators locate files, inspect application logs, manage directories, and clean up temporary resources. These skills are useful for cloud server administration and DevOps troubleshooting.
