# Day 5: Package Management, Disk, and Memory

## 🎯 Learning Objectives
Understand how to install system tools, monitor storage capacity, and check memory and uptime to ensure a healthy server environment.

---

## 🛠️ Commands Practiced Today

### 1. Package Management (`apt`)
*   `sudo apt update`: Downloads the latest package lists from the Ubuntu servers. Always run this before installing software.
*   `sudo apt install <package_name>`: Installs a new software package (e.g., `sudo apt install htop -y`).

### 2. Monitoring Memory and CPU
*   `htop`: An interactive, colorful process viewer that shows CPU and Memory (RAM) usage, plus running processes (press `q` to quit).

### 3. Monitoring Disk Space
*   `df -h`: (Disk Free) Shows the overall storage capacity and usage for all mounted filesystems in human-readable format (MB/GB).
*   `du -sh <folder_name>`: (Disk Usage) Calculates the exact size of a specific directory and summarizes it.

### 4. System Uptime
*   `uptime`: Displays how long the system has been running since the last reboot, how many users are logged in, and the system load averages.

---

## 🚀 Important Related Commands (For Future Reference)
*   `sudo apt upgrade -y`: Installs the newest versions of all packages currently installed on the system.
*   `sudo apt remove <package_name>`: Uninstalls a software package.
*   `free -m`: A non-interactive command to quickly see available and used RAM in megabytes.
