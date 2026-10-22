# Day 1 — Linux and DevOps Environment Setup

## 1. Objective

Set up a Linux learning environment on Windows, connect it with VS Code, create a GitHub repository, and practise basic Linux commands and filesystem operations.

## 2. Environment Setup

### Tools Used

- **Windows:** Host operating system.
- **WSL 2:** Runs Linux inside Windows.
- **Ubuntu:** Linux distribution used for practice.
- **Visual Studio Code:** Code editor connected to Ubuntu.
- **Git:** Version control system.
- **GitHub:** Online platform for storing and sharing code.

### Verify the Linux Environment

```bash
pwd
whoami
```

Expected output:

```text
/home/shravan
shravan
```

- `pwd` displays the current working directory.
- `whoami` displays the current Linux username.

## 3. GitHub Repository Setup

Repository name: `cloud-devops-90-days`

Purpose: Store daily learning notes, practical exercises, scripts, and DevOps projects.

### Useful Git Commands

```bash
git status
git add notes/day-01.md
git commit -m "docs: update Day 1 Linux practice notes"
git push
```

- `git status` checks the current state of the working tree.
- `git add` stages changes for a commit.
- `git commit` records staged changes locally.
- `git push` uploads committed changes to GitHub.

## 4. Basic Linux Commands

| Command | Purpose | Example |
|---|---|---|
| `pwd` | Display current directory | `pwd` |
| `whoami` | Display current username | `whoami` |
| `ls` | List visible files and directories | `ls` |
| `ls -a` | Include hidden files | `ls -a` |
| `ls -R` | List directory contents recursively | `ls -R` |
| `cd` | Change directory | `cd ~/projects` |
| `cd ~` | Go to the home directory | `cd ~` |
| `cd ..` | Go to the parent directory | `cd ..` |
| `mkdir` | Create a directory | `mkdir projects` |
| `mkdir -p` | Create nested directories | `mkdir -p cloud/devops/linux` |
| `touch` | Create an empty file | `touch config.txt` |
| `echo` | Print text or write it to a file | `echo "Hello"` |
| `cat` | Display file contents | `cat config.txt` |
| `cp` | Copy a file | `cp config.txt backup.txt` |
| `mv` | Move or rename a file | `mv old.txt new.txt` |

## 5. Understanding Directories and Paths

### What does `mkdir -p` do?

The `-p` option allows Linux to create missing parent directories when creating a nested path. It also avoids an error if the requested directories already exist.

Example:

```bash
mkdir -p cloud/devops/linux
```

This creates the following directory structure:

```text
cloud/
└── devops/
    └── linux/
```

Running the same command again does not create duplicate directories.

### Same Directory Names

Two directories can have the same name when they have different parent directories.

```text
projects/
└── cloud/

backup/
└── cloud/
```

These are different directories because their full paths differ.

### Absolute Paths

An absolute path specifies the complete location from the root directory `/`.

Example:

```bash
cd /home/shravan/projects/backup
```

### Relative Paths

A relative path specifies a location from the current directory.

Example, when the current directory is `/home/shravan/projects`:

```bash
cd backup
```

### Understanding `..`

The symbol `..` represents the parent directory.

If the current directory is:

```text
/home/shravan/projects/cloud
```

Run:

```bash
cd ../backup
```

Linux moves up to `projects` and then enters `backup`.

## 6. Linux Filesystem Practical Exercise

### Step 1: Create a directory structure

```bash
mkdir -p practice/server/logs
```

### Step 2: Enter the server directory

```bash
cd practice/server
```

### Step 3: Create a configuration file

```bash
touch config.txt
```

### Step 4: Write a message to the server log

```bash
echo "Server is running" > logs/server.log
```

The `>` operator redirects the output into a file. It creates the file if necessary and overwrites existing contents.

### Step 5: Read the log file

```bash
cat logs/server.log
```

Expected output:

```text
Server is running
```

### Step 6: Copy a file

```bash
cp config.txt config-backup.txt
```

### Step 7: Rename the copied file

```bash
mv config-backup.txt backup.txt
```

### Step 8: View the directory structure

From the `practice/server` directory:

```bash
ls -R
```

Alternatively, return to the repository root:

```bash
cd ~/cloud-devops-90-days
ls -R practice
```

Expected structure:

```text
practice/
└── server/
    ├── backup.txt
    ├── config.txt
    └── logs/
        └── server.log
```

## 7. Hidden Files in Linux

Linux treats filenames beginning with a dot (`.`) as hidden by convention.

Example:

```text
.env
.git
```

Use the following command to display hidden files:

```bash
ls -a
```

Hidden files are often used for configuration, environment variables, and application settings.

## 8. Important Concepts Learned

1. Linux commands can be used to navigate and manage a filesystem.
2. `mkdir -p` creates nested directories without failing when they already exist.
3. Absolute paths begin with `/`, whereas relative paths depend on the current directory.
4. `..` represents the parent directory.
5. `touch` creates an empty file when it does not already exist.
6. `cat` displays file contents.
7. `cp` copies files, while `mv` moves or renames them.
8. The `>` operator redirects output into a file and overwrites existing contents.
9. `ls -a` displays hidden entries.
10. Git records project changes, and GitHub stores pushed commits online.

## 9. How These Skills Relate to DevOps

Linux is widely used to manage cloud virtual machines, servers, application files, logs, and deployment environments.

These foundational commands will be useful when working with:

- Cloud servers and virtual machines.
- Application configuration files.
- Log inspection and troubleshooting.
- Shell scripting and automation.
- Docker containers.
- CI/CD pipelines.
- Infrastructure management.

## 10. Day 1 Summary

Today's work focused on preparing the development environment, connecting VS Code to Ubuntu, setting up the GitHub repository, and practising basic Linux filesystem operations.

The next step is to build stronger Linux skills through filesystem navigation, file searching, permissions, and other practical administration tasks.

## 11. GitHub Update

From the repository root, run:

```bash
cd ~/cloud-devops-90-days
git status
git add notes/day-01.md
git commit -m "docs: complete Day 1 Linux fundamentals"
git push
```

If Git reports that there is nothing to commit, check whether the notes have already been committed.

**Day 1 deliverable:** A documented Linux environment setup and a practical filesystem exercise stored in the GitHub repository.
