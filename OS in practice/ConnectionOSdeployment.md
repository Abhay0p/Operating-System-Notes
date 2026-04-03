# CLI & GUI Reference: Remote Access and OS Deployment

## 1. Remote Connection Concepts
* **Remote Access**: The ability to access a computer or a network from a remote distance.
* **SSH (Secure Shell)**: A protocol used to securely connect to a remote computer’s command line. It is the standard for Linux.
* **RDP (Remote Desktop Protocol)**: A Microsoft protocol that allows a user to connect to another computer over a network connection via a GUI.
* **PuTTY**: A popular, free open-source terminal emulator that supports SSH for Windows users to connect to Linux servers.
* **VPN (Virtual Private Network)**: Creates a secure "tunnel" over the internet, allowing a remote user to act as if they are directly connected to a private local network.

## 2. Linux Remote Management (SSH)
* **ssh [user]@[hostname_or_IP]**: The command to start a remote session.
    * Example: `ssh cindy@192.168.1.50`
* **Secure Copy (scp)**: Used to copy files between a local and remote host over SSH.
    * Example: `scp file.txt cindy@remote_host:/home/cindy`

## 3. Windows Remote Management
* **Remote Desktop Connection (mstsc.exe)**: The built-in Windows client for RDP.
* **PowerShell Remoting (WinRM)**: Allows you to run PowerShell commands on remote Windows machines.
    * `Enter-PSSession -ComputerName [Remote_PC]`

## 4. OS Deployment
* **Imaging**: Creating a "golden image" (a snapshot of a perfectly configured OS and apps) and deploying that exact copy to multiple machines.
* **Disk Cloning**: Copying the entire contents of one hard drive to another.
* **Network Boot (PXE)**: Allows a computer to boot up and install an operating system directly from a network server instead of a local USB or Disk.
* **Virtualization**: Running an "instance" of an OS within another OS using a Hypervisor (like VirtualBox or VMware). This is used to test software or run multiple servers on one physical machine.

## 5. Troubleshooting Remote Issues
* **Ping**: A utility used to test if a remote machine is reachable over the network.
* **Check the Service**: Ensure the SSH or RDP service is actually running on the target machine.
* **Firewalls**: Often the reason a connection is blocked; the specific port (SSH: 22, RDP: 3389) must be open.
