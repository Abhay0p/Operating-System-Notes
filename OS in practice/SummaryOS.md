# Module 6: Remote Connection, OS Deployment, and Automation

## 1. Remote Connection Concepts
* **Remote Access**: Accessing a computer or network from a distance.
* **SSH (Secure Shell)**: The standard for secure Linux CLI access. Encrypts the connection to prevent "sniffing."
* **RDP (Remote Desktop Protocol)**: Microsoft’s protocol for GUI-based remote access. 
* **PuTTY**: A free terminal emulator used on Windows to connect to Linux servers via SSH.
* **VPN (Virtual Private Network)**: A secure "tunnel" that makes a remote device appear as if it is on the local office network.
* **SSH Key Authentication**: A more secure alternative to passwords using a public and private key pair.

## 2. Remote Management (CLI)
* **Linux (SSH)**:
    * `ssh [user]@[IP]`: Start a remote session.
    * `scp [file] [user]@[IP]:[path]`: Securely copy a file to a remote machine.
* **Windows (PowerShell Remoting)**:
    * `Enter-PSSession -ComputerName [Name]`: Start an interactive remote shell.
    * **mstsc.exe**: The command to launch the "Remote Desktop Connection" GUI.

## 3. OS Deployment & Maintenance
* **Imaging**: Creating a "Golden Image" (snapshot) of a pre-configured OS to deploy to hundreds of machines.
* **Disk Cloning**: A 1:1 copy of one hard drive to another.
* **Network Boot (PXE)**: "Preboot Execution Environment." Allows a computer to boot and install an OS from a network server instead of a local disk.
* **Virtualization**: Running an "instance" of an OS inside another OS using a **Hypervisor** (e.g., VirtualBox, VMware, Hyper-V).
* **Logs (The IT Diary)**:
    * **Windows Event Viewer**: View Application, Security, and System logs.
    * **Linux `/var/log`**: Central location for text-based logs (e.g., `syslog`, `auth.log`).

## 4. I/O Streams & Redirection (The "Water" Analogy)
* **The Three Streams**:
    1. **stdin (0)**: Input (Keyboard).
    2. **stdout (1)**: Normal Output (Screen).
    3. **stderr (2)**: Error messages.
* **Operators**:
    * `>` : Overwrites a file.
    * `>>` : Appends to a file.
    * `2>` : Redirects only errors (e.g., `rm file 2> errors.txt`).
* **The "Black Hole" (Hiding Errors)**:
    * Windows: `command 2> $null`
    * Linux: `command 2> /dev/null`
* **Pipes (|)**: Sends the output of one command into the input of the next.
    * Example: `ls | grep "test"`

## 5. Advanced Search & Automation
* **grep (Linux)**: Search text. `-r` (recursive), `-w` (whole word).
* **sls / Select-String (Windows)**: Search text in PowerShell.
* **ls -Filter (Windows)**: Pattern matching for file types (e.g., `*.exe`).
* **Echo**: Prints text or creates files via redirection (`echo "text" > file.txt`).

## 6. Troubleshooting Remote Issues
* **Ping**: Tests if a remote IP is reachable.
* **Port Numbers**: Standard ports must be open in the firewall:
    * **SSH**: Port 22
    * **RDP**: Port 3389
* **Service Status**: Verify that the remote service (SSH daemon or RDP service) is running.
