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

# Day 2 — Linux Quick Revision

## 1. Navigation

| Command | Use |
|---|---|
| `pwd` | Show current directory |
| `ls` | List visible files |
| `ls -a` | Show hidden files |
| `ls -l` | Detailed file listing |
| `ls -R` | List recursively |
| `cd ~` | Go to home directory |
| `cd .` | Stay in current directory |
| `cd ..` | Go up one directory |

**Paths:** Absolute paths start with `/`; relative paths start from your current location.

## 2. Create and Manage Files

| Command | Use |
|---|---|
| `mkdir -p a/b` | Create nested directories |
| `touch file.txt` | Create an empty file |
| `cp a.txt backup/` | Copy a file |
| `mv old.txt new.txt` | Move or rename a file |
| `cat file.txt` | Display file contents |

## 3. Write to Files

```bash
echo "Hello" > file.txt
echo "Another line" >> file.txt
```

- `>` replaces existing contents or creates a file.
- `>>` appends without replacing existing contents.
- `cat > file.txt <<'EOF'` lets you enter multiple lines until `EOF`.

## 4. Read Logs

| Command | Use |
|---|---|
| `head -n 5 file.log` | First 5 lines |
| `tail -n 5 file.log` | Last 5 lines |
| `tail -f file.log` | Follow new log entries |
| `less file.log` | Scroll through a file; press `q` to quit |

## 5. Find Files

```bash
find practice -name "*.log"
find practice -iname "ERROR.LOG"
find practice -type f
find practice -type d
```

- `-name` — case-sensitive name matching.
- `-iname` — case-insensitive name matching.
- `-type f` — files only.
- `-type d` — directories only.
- `*` — wildcard matching zero or more characters in a shell pattern.

## 6. Delete Safely

| Command | Use |
|---|---|
| `rm -i file.txt` | Ask before deleting |
| `rm file.txt` | Delete a file without interactive confirmation |
| `rmdir folder` | Delete an empty directory |
| `rm -r folder` | Delete a directory and its contents recursively |

**Warning:** `rm` generally does not use a recycle bin. Check the target before deleting.

## 7. DevOps Practical Workflow

```bash
mkdir -p practice/app/{config,logs,backup}
touch practice/app/config/app.conf
echo "Application started" > practice/app/logs/app.log
echo "Warning: high memory" >> practice/app/logs/app.log
tail -n 2 practice/app/logs/app.log
find practice/app -type f
cp practice/app/logs/app.log practice/app/backup/
ls -R practice/app
```

This practises directory creation, log writing, log inspection, file searching, copying, and verification.

## 8. Save Your Work to GitHub

```bash
git status
git add notes practice
git commit -m "docs: complete Day 2 Linux practice"
git push origin main
git status
```

- `git add` — stage changes.
- `git commit` — save a local snapshot.
- `git push` — upload commits to GitHub.
- Final `git status` — check whether the working tree is clean.

## Remember These 5 Things

1. `.` = current directory; `..` = parent directory.
2. `>` overwrites; `>>` appends.
3. `head` reads from the beginning; `tail` reads from the end.
4. `find` searches; `cp` copies; `mv` moves or renames.
5. `rm -i` asks for confirmation; `rmdir` only removes empty directories.
