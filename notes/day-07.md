# Day 7: Linux System Health and Log Analyzer

A lightweight, automated Bash script designed for daily server monitoring and system health checks, built as the Week 1 portfolio project for my Cloud & DevOps engineering roadmap.

## 📝 Overview

In a production environment, engineers need a quick and reliable way to assess server health before escalating issues or diving into advanced monitoring tools like Prometheus or Grafana. 

This script combines core Linux administration commands to parse system metrics, evaluate threshold conditions, and generate a clean, color-coded report covering uptime, resource utilization, and recent log errors.

### Key Features & What It Checks:
1. **System Uptime & Load:** Displays how long the machine has been running along with current CPU load averages.
2. **Disk Usage:** Calculates utilization of the Root partition (`/`) and triggers a custom red warning if capacity exceeds the defined threshold.
3. **Memory Usage:** Pulls total, used, and free system RAM in a human-readable format.
4. **Top CPU-Consuming Process:** Automatically identifies and lists the process currently consuming the most CPU resources.
5. **System Log Analysis:** Scans system logs via `journalctl` to surface recent errors or failures.

---

## 🚀 Setup & Execution

### Prerequisites
* A Linux environment (Ubuntu, Debian, CentOS, WSL2, etc.)
* Standard terminal access with Bash interpreter.

### Instructions
1. **Clone the repository:**
   ```bash
   git clone https://github.com/Shravan96-Cloud/linux-system-health-monitor.git
   ```
2. **Navigate into the directory:**
   ```bash
   cd linux-system-health-monitor
   ```
3. **Ensure the script has execution permissions:**
   ```bash
   chmod +x health_check.sh
   ```
4. **Run the script:**
   ```bash
   ./health_check.sh
   ```

---

## 🛠️ Technologies & Commands Used
* **Scripting Language:** Bash (`/bin/bash`)
* **Core Linux Utilities:** 
  * `uptime` & `date` — System timing and uptime tracking.
  * `df` & `free` — Storage and memory resource inspection.
  * `ps` — Active process filtering and sorting.
  * `journalctl` — Systemd journal log querying.
* **Text Processing:** `awk` (column extraction and field separation) and `sed` (string substitution).
* **Version Control:** Git & GitHub.

---

## 💡 Lessons Learned & Technical Challenges

The biggest challenge during development was learning how to take raw, unstructured terminal output and parse it cleanly. By chaining pipes (`|`) with `awk` and `sed`, I learned how to strip unnecessary characters (like removing `%` signs from `df` outputs) so that variables could be evaluated numerically inside Bash `if` statements (e.g., `-gt` comparisons). 

This project bridged the gap between running isolated manual commands and combining them into an automated, reusable operational tool.

---

## 🔗 Project Repository
* **GitHub Link:** [linux-system-health-monitor](https://github.com/Shravan96-Cloud/linux-system-health-monitor)