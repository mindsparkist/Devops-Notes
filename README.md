Welcome to the world of DevOps! Think of the Linux File System as the "Source of Truth." In DevOps, you aren’t just using a computer; you’re managing environments. Understanding where files live and how to move them is the difference between a smooth deployment and a "Why is the server down?" 3 AM phone call.

---

## 1. The Prompt: `username@computer:~$`
Before you type a single command, you need to know where you are. This string is your **bash prompt**.

* **`username`**: Who you are (permissions depend on this).
* **`@computer`**: The name of the server (critical when managing 50+ servers).
* **`~` (The Tilde)**: This is shorthand for your **Home Directory**.
* **`$`**: Means you are a standard user. If you see a **`#`**, you have **root** (admin) privileges—tread carefully!

---

## 2. Home Directories: A Comparison
Every OS gives the user a "personal bubble" to store files.

| OS | Default Home Path |
| :--- | :--- |
| **Linux (Ubuntu/RedHat)** | `/home/username` |
| **macOS** | `/Users/username` |
| **Windows** | `C:\Users\username` |

**DevOps Note:** In Linux, the **root user** is special. Their home directory isn't in `/home`; it’s just `/root`.

---

## 3. The Linux Directory Hierarchy (FHS)
Linux follows the **Filesystem Hierarchy Standard**. Everything starts at `/` (the root).



* **`/bin` & `/sbin`**: Essential binaries (programs). `/sbin` is usually for system admin tools (like `fdisk`).
* **`/lib`**: Shared library files that programs need to run (like `.dll` files in Windows).
* **`/etc`**: **The most important folder for DevOps.** This is where configuration files live (Nginx config, Docker config, etc.).
* **`/home`**: User folders (e.g., `/home/ram`, `/home/sam`).
* **`/boot`**: Files needed to start the OS.
* **`/dev`**: Hardware access points (everything in Linux is a file, even your hard drive).
* **`/opt`**: Optional/add-on software (where large third-party apps often install).
* **`/var`**: Variable data. **`/var/log`** is your best friend when debugging.
* **`/tmp`**: Temporary files (often cleared on reboot).
* **`/proc`**: A "virtual" filesystem containing info about running processes and system resources.

---

## 4. The "Survival" Command Set
As a Junior DevOps Engineer, these should be in your muscle memory:

### Navigation & Discovery
* **`pwd`**: "Print Working Directory." (Where am I?)
* **`ls`**: List files. Use `ls -la` to see hidden files and permissions.
* **`cd`**: Change directory.
    * `cd ..`: Move up one level.
    * `cd ~`: Go straight home.

### File Manipulation
* **`mkdir`**: Create a folder.
* **`touch`**: Create an empty file.
* **`nano`**: A simple text editor. (Great for quick config edits).
* **`cp`**: Copy files.
    * `cp -R source/ destination/`: The **`-R`** stands for **Recursive**. Use this to copy entire folders.
* **`mv`**: Move or **rename** a file.
    * Example: `mv todo.txt /tmp/test` moves the file to the temp folder.
* **`rm`**: Remove.
    * **Warning:** `rm -rf` deletes recursively and forcefully. It doesn't ask "Are you sure?" Use with extreme caution.

---

### Pro-Tip for your Journey
In DevOps, we rarely do things manually twice. Once you master these commands, your next step is learning how to put them into a **Bash Script** to automate your work.
