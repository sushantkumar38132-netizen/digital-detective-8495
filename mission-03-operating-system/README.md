# Mission 3 — Understand the operating system

## 1. Task / objective
The objective of this mission is to explore core operating system functions:
- Gather and interpret system specifications, user identity, disk storage, and active processes via the CLI.
- Understand the definition of a process and how the OS tracks it using Process Identifiers (PIDs).
- Differentiate between absolute and relative paths, and examine file permission structures (`r`, `w`, `x`).
- Analyze the six primary responsibilities of a modern operating system.

---

## 2. Work completed
- **Task 3.1:** Queried and documented privacy-safe system details (`sw_vers`, `whoami`, `df -h`, and process snapshot).
- **Task 3.2:** Analyzed running system processes, identified the PID column, and answered the conceptual process questions.
- **Task 3.3:** Demonstrated navigation with absolute and relative paths, inspected file permissions (`ls -l`), and verified owner permissions.
- **Task 3.4:** Completed the detailed Operating System Responsibilities table with descriptions and real-world examples.

---

## 3. Commands / tools used

| Command / Tool | Purpose |
| :--- | :--- |
| `sw_vers` / `uname` | Displays the operating system product name, version, and kernel build. |
| `whoami` | Identifies the currently active user account name. |
| `df -h` | Reports filesystem disk space usage, capacity, and mount points in human-readable units. |
| `ps aux` / `top` | Captures a snapshot of currently active processes, CPU/memory consumption, and PIDs. |
| `ls -l` | Displays detailed file attributes, including ownership and POSIX permission bits (`rwx`). |
| `pwd` / `cd` | Verifies current working directory and navigates through relative and absolute folder paths. |
| `git` | Stages, commits, and pushes mission documentation to the GitHub repository. |

---

## 4. Understanding

### Task 3.1 — Explore your operating system

| Information explored | What it tells you | Your observation (privacy-safe) |
| :--- | :--- | :--- |
| **Operating system / system details** | Identifies the OS distribution, version number, and build identifier running on the machine. | `macOS Version 27.2` |
| **Current account identity** | Displays the username of the account executing commands in the current shell session. | `[redacted]` |
| **Available and used storage** | Shows total storage capacity, used disk space, remaining free space, and mount partition. | Root partition `/`: Size: `460Gi`, Used: `13Gi`, Available: `312Gi` (Capacity: `4%`) |
| **System activity snapshot** | Displays a real-time list of executing programs, their process IDs, CPU load, and memory allocation. | Active processes running: `WindowServer`, Browser/Editor helper processes. |

---

### Task 3.2 — Understand processes

1. **What is a process?**
   - A process is an active, executing instance of a computer program loaded into primary memory (RAM). It possesses its own allocated memory space, system resources, and execution state managed by the OS kernel.

2. **What does the PID column represent?**
   - The **PID (Process Identifier)** is a unique positive integer assigned by the operating system kernel to every active process. It allows the OS to track, schedule, prioritize, and terminate (`kill`) individual processes without ambiguity.

3. **Give two examples of processes that may be running on your computer:**
   - **`WindowServer` (Background system daemon):** Manages the graphical display server, compositing windows, rendering user interfaces, and routing input events on macOS.
   - **`python3` / `code` (Application process):** The Python interpreter executing a script, or the text editor process managing the user workspace.

---

### Task 3.3 — Understand paths and permissions

#### 1. Absolute vs Relative Paths
- **Absolute Path:** The complete, unambiguous location of a file or directory starting from the root directory (`/`). It does not depend on your current location.
- **Relative Path:** The location of a file or directory calculated relative to your current working directory.

#### 2. File Permissions Inspection
Inspected by `ls -l mission-03-operating-system/README.md`:
- Output permission string: `-rw-r--r--`
- **Permission Breakdown for Owner:**
  - **Read (`r`):** **Yes** — The owner has permission to open and read file contents.
  - **Write (`w`):** **Yes** — The owner has permission to edit, update, or overwrite the file.
  - **Execute (`x`):** **No (`-`)** — The file is a plain markdown document and is not flagged as an executable program or script.

---

### Task 3.4 — Explain operating-system responsibilities

| OS responsibility | Your explanation | Example |
| :--- | :--- | :--- |
| **Process management** | Controls process creation, CPU scheduling, execution time-slicing, and termination to allow multitasking. | Switching CPU focus seamlessly between a web browser and code editor. |
| **Memory management** | Allocates and tracks blocks of RAM for active programs and frees memory when applications close. | Allocating 400 MB of RAM to a browser tab, and reclaiming it when the tab is closed. |
| **Device management** | Communicates with hardware peripherals using specialized device drivers and handles input/output requests. | Sending rasterized print commands through a USB or network printer driver. |
| **File management** | Organizes non-volatile storage into hierarchical files and directories, tracking paths, metadata, and access permissions. | Creating, saving, moving, or deleting files. |
| **User interface / shell** | Provides a graphical user interface (GUI) or command-line interface (CLI) for users to interact with system services. | Running commands in the macOS Terminal shell (`zsh`) or opening apps via Finder. |
| **Security and permissions** | Enforces access control policies, authenticates users, and isolates memory so processes cannot corrupt one another. | Requiring a password/Touch ID to install software and preventing normal users from editing system files. |

---

## 5. Difficulties faced
- Ensuring that all terminal outputs and path examples complied with privacy rules by redacting usernames and hostnames.

---

## 6. How I resolved it
- Replaced personal account paths and user IDs with placeholders in all logs and tables.

---

## 7. Evidence
- N/A

---

## 8. Commit details
- **Commit Message:** `Document operating system and file management`
- git commit -m "Document operating system and file management"