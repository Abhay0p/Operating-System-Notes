# Google IT Support Professional Certificate: Study Notes
## Course 3: Operating Systems and You: Becoming a Power User

> **Note:** These are personal Coursera notes I have saved for myself to master the Windows and Linux operating systems. They cover core components, command-line mastery, and IT Support troubleshooting workflows.

---

## 📂 Module Directory

### [Module 1: Navigation and File Management](./Module_1_Navigation.md)
* **Focus**: OS Architecture (Kernel vs. User Space), Directory Hierarchies, and Basic CLI.
* **Key Skills**: Navigating paths, viewing hidden files, and standard I/O redirection.

### [Module 2: Users, Groups, and Permissions](./Module_2_Permissions.md)
* **Focus**: Identity management and security.
* **Key Skills**: Windows ACLs (DACL/SACL), Linux 10-bit permission strings, and Privilege Escalation (Sudo/UAC).

### [Module 3: Software Management](./Module_3_Software.md)
* **Focus**: How software is packaged, installed, and managed.
* **Key Skills**: Package Managers (APT/Chocolatey), DLL troubleshooting (WinSxS), and Shared Libraries.

### [Module 4: File Systems and Disk Management](./Module_4_Filesystems.md)
* **Focus**: Physical and logical storage.
* **Key Skills**: Partition tables (MBR/GPT), Journaling, Formatting, and Mounting drives in Linux.

### [Module 5: Process Management](./Module_5_Processes.md)
* **Focus**: Managing active tasks and system resources.
* **Key Skills**: Task Manager vs. Top, Process Signals (Kill -9 vs -15), and identifying Memory Leaks.

### [Module 6: Remote Access and OS Deployment](./Module_6_Deployment.md)
* **Focus**: Managing fleets of computers and remote troubleshooting.
* **Key Skills**: SSH/RDP, Imaging (Sysprep), Virtualization, and Network Booting (PXE).

---

## 🛠️ Master Toolset Summary
* **Windows**: PowerShell, Computer Management, icacls, net user.
* **Linux**: Bash Shell, sudo, chmod/chown, apt, ps/top.

## 💡 Study Strategy
1. **The Principle of Least Privilege**: Always work with the lowest permissions possible.
2. **Logs are the Diary**: When in doubt, check Event Viewer (Win) or /var/log (Linux).
3. **Tab Completion is Life**: Never type full paths; let the shell finish them for you.
