# Day 4: Processes and Services

## 🎯 Learning Objectives
Understand how to monitor running applications, safely terminate unresponsive programs, and investigate background service health.

---

## 🧠 Core Concepts
*   **Process:** An instance of a running program. Every command you run creates a process with a unique Process ID (PID).
*   **Service (Daemon):** A background program that runs continuously (like a web server or `cron`), managed by `systemd`.
*   **Graceful vs. Force Kill:** `kill <PID>` asks a program to shut down safely. `kill -9 <PID>` forces it to terminate instantly.

---

## 🛠️ Commands Practiced Today

### Monitoring Processes
*   `ps aux`: Lists all currently running processes, showing the user, PID, CPU/Memory usage, and the command running.
*   `top`: Provides a live, constantly updating view of system resource usage (press `q` to quit).

### Terminating Processes
*   `sleep 600 &`: Starts a process in the background (`&`).
*   `kill <PID>`: Terminates the process matching the specified PID. 

### Managing Services and Logs
*   `systemctl status cron`: Checks the health and current status (active/inactive) of the `cron` service.
*   `sudo journalctl -u cron -n 10`: Queries the system logs specifically for the `cron` service, showing only the 10 most recent lines.

---

## 🚀 Important Related Commands (For Future Reference)
*   `killall process_name`: Kills all instances of a process by name (e.g., `killall node`).
*   `sudo systemctl restart service_name`: Restarts a service (crucial when applying new configuration files).
*   `sudo systemctl enable service_name`: Configures a service to start automatically when the server boots up.
