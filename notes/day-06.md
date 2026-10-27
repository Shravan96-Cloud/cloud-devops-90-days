# Day 6: Git and GitHub Workflows

## 🎯 Learning Objectives
Master the daily Git operations used in DevOps environments, including branching, merging, syncing with remote repositories, and resolving merge conflicts.

---

## 🧠 Core Concepts
*   **Branch:** An independent line of development. The default stable branch is usually `main`. Creating a feature branch allows you to experiment safely.
*   **Merge:** The process of taking the code from a feature branch and combining it into the `main` branch.
*   **Merge Conflict:** Occurs when two branches modify the exact same line of code differently, and Git requires a human to manually resolve the differences before merging.
*   **Remote (`origin`):** The version of your repository hosted on a server (like GitHub) that you sync your local code with.

---

## 🛠️ Commands Practiced Today

### Branching and Merging
*   `git checkout -b <branch_name>`: Creates a new branch and switches to it immediately.
*   `git branch`: Lists all local branches and shows which one you are currently on.
*   `git checkout main`: Switches back to the `main` branch.
*   `git merge <branch_name>`: Takes the commits from the specified branch and integrates them into your current branch.

### Remote Operations
*   `git push origin main`: Uploads your local `main` branch commits to the remote repository on GitHub.
*   *(Note: `git pull origin main` is used to download updates from GitHub to your local machine).*

### Resolving Merge Conflicts
When a merge conflict occurs, Git modifies the affected files to show both versions.
1.  Open the file (e.g., `nano file.txt`).
2.  Locate the conflict markers (`<<<<<<< HEAD`, `=======`, `>>>>>>> branch_name`).
3.  Delete the markers and edit the code to the correct final version.
4.  Save the file.
5.  Run `git add <file>` and `git commit` to finalize the merge.
