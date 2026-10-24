# Day 3: Linux Permissions and Ownership

## 🎯 Learning Objectives
Understand how Linux handles file access, user privileges, and ownership to effectively troubleshoot "Permission Denied" errors and secure server environments.

---

## 🧠 Core Concepts

### 1. Permission Target Levels
Every file and directory in Linux has access rights defined for three levels of users:
*   **User (u):** The owner of the file.
*   **Group (g):** Users belonging to the file's assigned group.
*   **Others (o):** Everyone else on the system.

### 2. Permission Types & Numeric Values (Octal)
*   **Read (`r`) = 4:** View file contents or list a directory.
*   **Write (`w`) = 2:** Modify/delete a file, or add/remove files in a directory.
*   **Execute (`x`) = 1:** Run a script or navigate into a directory.
*   **No Permission (`-`) = 0**

*Example:* `755` means User gets `7` (4+2+1=rwx), Group gets `5` (4+1=r-x), and Others get `5` (4+1=r-x).

### 3. Superuser (`root`) & `sudo`
The `root` user has absolute administrative power. Regular users must use `sudo` (SuperUser DO) to temporarily elevate privileges for administrative tasks like changing file ownership[cite: 3].

---

## 🛠️ Commands Practiced Today

### Inspecting Files and Users
*   `ls -l`: Lists files in long format, revealing permission strings (e.g., `-rw-r--r--`) and ownership.
*   `groups`: Displays all groups the current user belongs to.
*   `getent group users`: Queries the system to list all specific users assigned to the 'users' group.

### Modifying Permissions (`chmod`)
*   `chmod u+x deployment_script.sh`: (Symbolic) Adds execute permission for the **u**ser (owner).
*   `chmod 755 deployment_script.sh`: (Numeric) Sets standard execute permissions for scripts/directories (`rwxr-xr-x`).
*   `chmod 644 app_config.txt`: (Numeric) Sets standard read/write permissions for standard files (`rw-r--r--`).

### Modifying Ownership (`chown`)
*   `sudo chown root:root app_config.txt`: Changes the owner and group of the file to the `root` superuser.
*   `sudo chown shravan:shravan app_config.txt`: Restores the owner and group back to the standard user (`shravan`).

---

## 🚀 Important Related Commands (For Future Reference)

While we didn't practice these today, these commands are essential for Linux administration and CI/CD pipelines:

### Recursive Operations
*   `chmod -R 755 /path/to/folder`: Changes permissions for a directory and *everything* inside it recursively.
*   `chown -R www-data:www-data /var/www/html`: Changes ownership recursively (very common when deploying web servers like Nginx or Apache).

### User and Group Management
*   `sudo useradd username`: Creates a new user on the system.
*   `sudo usermod -aG sudo username`: Adds an existing user to a supplementary group (in this case, granting them `sudo` privileges).
*   `sudo userdel username`: Deletes a user.
*   `sudo groupadd devops`: Creates a new group named 'devops'.

### Advanced Access
*   `umask`: Displays or sets the default permissions applied to newly created files and directories.
*   `su - username`: Switches your current terminal session to act as another user entirely.
