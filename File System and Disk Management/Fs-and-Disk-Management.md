# Module 4: File Systems and Disk Management

## 1. Core Concepts & Disk Geometry
* **File System**: The OS's "map" for the hard drive. It decides how data bits are named, stored, and retrieved.
* **Partitioning**: Dividing a physical disk into logical sections or "rooms." You must partition a disk before it can be formatted.
* **Partition Tables (The Standards)**:
    * **MBR (Master Boot Record)**: Old standard. Supports up to 4 primary partitions and disk sizes only up to 2TB.
    * **GPT (GUID Partition Table)**: Modern standard. Supports nearly unlimited partitions and disks larger than 2TB. Required for modern UEFI booting.
* **Formatting**: The process of applying a specific file system (like NTFS) to a partition so the OS can read and write data.
* **Journaling**: A safety feature in modern file systems (NTFS, ext4). It keeps a log of changes to be made. If the computer crashes, the "journal" helps recover data and prevent corruption.

## 2. File System Types & Comparison
* **NTFS (New Technology File System)**: Default for Windows. Supports ACLs (permissions), encryption, and **Journaling**.
* **FAT32**: High compatibility across Windows, Linux, Mac, and Cameras.
    * **Major Limit**: Maximum individual file size is **4GB**.
* **ext4**: The standard high-performance journaling file system for most Linux distributions.
* **APFS**: The modern, high-speed file system used by Apple (macOS and iOS).

## 3. Storage Expansion: Mounting & Virtual RAM
* **Mounting**:
    * **Windows**: Uses **Drive Letters** (C:, D:, X:). Each letter represents a separate file system.
    * **Linux**: Uses **Mount Points**. A drive is "attached" to a folder (e.g., `/mnt/usb`). If you unmount it, the folder appears empty.
* **Swap/Paging**: Using a portion of the hard drive as "Virtual RAM" when physical RAM is full.
    * Windows: Called **Paging**.
    * Linux: Called **Swap**.

## 4. Windows Management (GUI & CLI)
* **Disk Management Tool**: The primary GUI hub to initialize disks, create partitions, format, and change drive letters.
* **Disk Cleanup**: A built-in utility to delete temporary system files and free up space.
* **Defragmentation**: Rearranges file fragments into contiguous blocks on a physical **HDD** to speed up access. 
    * **Warning**: Never defrag an **SSD**, as it reduces the drive's lifespan without adding speed.
* **chkdsk /f**: CLI command ("Check Disk") used to scan for and fix file system errors.

## 5. Linux Management (CLI)
* **lsblk**: "List Block Devices." Shows all connected drives, their partitions, and where they are mounted.
* **mount [device] [folder]**: Attaches a partition to a directory. 
    * Example: `sudo mount /dev/sdb1 /home/cindy/external`
* **umount [folder]**: Detaches the drive. (Note: The command is `umount`, no "n").
* **df -h**: "Disk Free." Shows available space on all mounted systems in human-readable (GB/MB) format.
* **du -sh [directory]**: "Disk Usage." Shows the total size of a specific folder or file.
* **fsck**: "File System Check." The Linux version of chkdsk. Used to repair partitions. 
    * **Rule**: Must be run while the drive is **unmounted**.

## 6. Troubleshooting & Best Practices
* **Low Disk Space**: Can lead to "unusual errors," failed updates, and slow performance.
* **Cloud Integration**: Encourage users to use Cloud storage for large media (photos/videos) to keep local storage free for apps and the OS.
* **Identifying Drives**: In Linux, `/dev/sda` is usually the first physical disk, and `/dev/sda1` is the first partition on that disk.
