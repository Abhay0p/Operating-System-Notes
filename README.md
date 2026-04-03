# Google IT Support Professional Certificate: Study Notes
## Course 3: Operating Systems and You: Becoming a Power User

> **Note:** These are personal Coursera notes I have saved for myself to master the Windows and Linux operating systems. They cover core components, command-line mastery, and IT Support troubleshooting workflows.

---

## 📂 Course Modules

### 📁 [File Management](./File%20Management/)
* **Core Topics**: OS Architecture, Navigation, Basic Commands, and I/O Redirection.
* **Key Skills**: `cd`, `ls`, `mkdir`, and mastering the 3 Standard Streams (stdin, stdout, stderr).

### 📁 [UsersAndPermissions](./UsersAndPermissions/)
* **Core Topics**: User Identity, Group Management, and Access Control Lists (ACLs).
* **Key Skills**: Windows `icacls`, Linux `chmod`/`chown`, and the Principle of Least Privilege.

### 📁 [Package and Software Management](./Package%20and%20Software%20Management.../)
* **Core Topics**: Package Managers, Dependencies, Shared Libraries, and Drivers.
* **Key Skills**: `apt` (Linux), Chocolatey (Windows), and troubleshooting "DLL Hell."

### 📁 [File System and Disk Management](./File%20System%20and%20Disk%20Management/)
* **Core Topics**: Partitioning (MBR/GPT), Formatting, Mounting, and Virtual RAM.
* **Key Skills**: `lsblk`, `mount`, `fdisk`, and managing NTFS/ext4/FAT32 systems.

### 📁 [Process Management](./Process%20Management/)
* **Core Topics**: Task monitoring, PID tracking, and System Signals.
* **Key Skills**: Task Manager, `top`, `ps aux`, and the `kill` command (SIGTERM vs. SIGKILL).

### 📁 [OS in practice](./OS%20in%20practice/)
* **Core Topics**: Remote Access (SSH/RDP), Deployment (Imaging/PXE), and Troubleshooting.
* **Key Skills**: `ssh`, `scp`, PowerShell Remoting, and analyzing system logs.

---

## 🛠️ Master Toolset Summary
* **Windows**: PowerShell, Computer Management, Registry, Event Viewer.
* **Linux**: Bash Shell, sudo, Repository management, /var/log.

## 💡 Pro-Tips for IT Support
1. **Pipes are Powerful**: Use `|` to chain commands together for faster troubleshooting.
2. **Logs don't lie**: When a system fails, the answer is usually in the Event Viewer or Syslog.
3. **Automate the Boring Stuff**: If you have to do it twice, write a script.
