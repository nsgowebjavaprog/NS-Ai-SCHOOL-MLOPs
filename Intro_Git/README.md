# Git interview Ready Roadmap and Q&A

Download and Setup the git and github in your device [click to download](https://github.com/).

Create a 1 repo and copy URL paste in vs code editor and move forward...

----------------------------------------------------------------

1. ls – List files and directories.

2. ls -a – List all files including hidden files.

3. rm -rf <dir> – Remove directories recursively (be careful!).

4. cd <dir> – Change directory.

5. pwd – Print current working directory.

6. mkdir <dir> – Create a new directory.

7. touch <file> – Create an empty file.

8. cp <src> <dest> – Copy files or directories.

9. mv <src> <dest> – Move or rename files/directories.

10. cat <file> – View file contents.

11. tail -f <logfile> – Follow logs in real-time (important for monitoring ML pipelines).

12. grep <pattern> <file> – Search for patterns in files.

13. find <path> -name <filename> – Search files or directories recursively.

14. chmod +x <file> – Make a file executable (for scripts).

15. chown user:group <file> – Change ownership of files.

16. df -h – Show disk usage in human-readable format.

17. du -sh <dir> – Show folder size summary.

18. ps aux | grep <process> – Check running processes (like ML training scripts).

19. kill -9 <pid> – Terminate a process by PID.

20. scp <file> user@host:/path – Copy files to remote servers (for transferring models/data).



Here’s a **job-ready, concise, and structured answer** for each Git/MLOps/Data Science interview question. I’ve made it professional and easy to memorize.

---

### **1. What is Git and what are advantages of it?**

**Answer:**
Git is a **distributed version control system (DVCS)** that tracks changes in source code during software development. It allows multiple developers to work simultaneously without overwriting each other’s changes.

**Advantages:**

* **Distributed system:** Each developer has a full repository copy.
* **Fast and efficient:** Local operations are fast.
* **Branching and merging:** Easy to create and merge branches.
* **Data integrity:** Uses SHA-1 hashing to track changes.
* **Collaboration:** Supports multiple workflows and team collaboration.

---

### **2. What is SCM in Git and what are advantages of it?**

**Answer:**
SCM stands for **Source Code Management**. Git is an SCM tool used to manage code versions and changes.

**Advantages of SCM in Git:**

* Keeps **track of every code change**.
* Enables **collaboration** among multiple developers.
* **Reverts** code to a previous stable version if needed.
* Maintains a **history** of changes with authorship.
* Supports **branching and merging** workflows.

---

### **3. What is Version Control in Git and what are advantages of it?**

**Answer:**
**Version Control** is a system that records changes to files over time so you can recall specific versions later.

**Advantages:**

* Tracks **history of files**.
* Allows **rollback** to previous versions.
* Enables **multiple developers** to work on the same project.
* Reduces the risk of **code loss**.
* Simplifies **debugging and collaboration**.

---

### **4. What are help commands to use in Git?**

**Answer:**

* `git help` – Show Git commands help.
* `git help <command>` – Detailed help for a specific command.
* `git <command> --help` – Another way to get command-specific help.

Example:

```bash
git help commit
```

---

### **5. How Git Works Internally?**

**Answer:**
Git stores data as **snapshots of the project** rather than differences.

* **Local folder:** Where you write code.
* **Working directory:** Your current local code files.
* **Staging area (Index):** Where you prepare changes to commit.
* **Local repository:** `.git` folder stores commit history and snapshots.
* **Remote repository:** Central repository (like GitHub) to collaborate.

**Flow:** Working Directory → Staging Area → Local Repo → Remote Repo

---

### **6. What is Staging and Committing in Git?**

**Answer:**

* **Staging (Index):** Temporary area to **prepare changes** before committing.
* **Commit:** Saves the staged changes **permanently** in the local repository with a message describing the change.

**Example:**

```bash
git add file.txt    # Stage
git commit -m "Added new feature"   # Commit
```

---

### **7. Top 20 Important Git Commands with Explanation and Example**

| Command        | Explanation               | Example                                |
| -------------- | ------------------------- | -------------------------------------- |
| `git init`     | Initialize a new Git repo | `git init`                             |
| `git clone`    | Clone remote repo locally | `git clone url`                        |
| `git status`   | Show repo status          | `git status`                           |
| `git add`      | Add files to staging area | `git add file.txt`                     |
| `git commit`   | Save changes to repo      | `git commit -m "msg"`                  |
| `git log`      | Show commit history       | `git log`                              |
| `git diff`     | Show unstaged changes     | `git diff`                             |
| `git branch`   | List/create branches      | `git branch dev`                       |
| `git checkout` | Switch branch             | `git checkout dev`                     |
| `git merge`    | Merge branches            | `git merge dev`                        |
| `git remote`   | Manage remotes            | `git remote add origin url`            |
| `git push`     | Push to remote            | `git push origin main`                 |
| `git pull`     | Pull from remote          | `git pull origin main`                 |
| `git fetch`    | Fetch from remote         | `git fetch origin`                     |
| `git reset`    | Undo changes              | `git reset --hard HEAD~1`              |
| `git rm`       | Remove file from repo     | `git rm file.txt`                      |
| `git stash`    | Save changes temporarily  | `git stash`                            |
| `git tag`      | Tag a commit              | `git tag v1.0`                         |
| `git show`     | Show commit details       | `git show HEAD`                        |
| `git config`   | Configure Git             | `git config --global user.name "John"` |

---