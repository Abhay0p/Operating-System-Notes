# CLI & GUI Reference: File Systems and Disk Management

## 1. Key Concepts
* **File System**: The method an OS uses to store, retrieve, and organize data. It acts as a map for the hard drive.
* **Partitioning**: Dividing a physical hard drive into logical sections. You must partition a disk before you can format it.
* **Formatting**: The process of creating a file system on a partition so the OS can read and write data.
* **Mounting**: Attaching a file system to a specific directory (mount point) to make it accessible to the user.
* **Drive Letters (Windows)**: Windows assigns file systems to letters (C:, D:, X:). Each letter represents a separate file system.
* **Swap/Paging**: Using a portion of the hard drive as "Virtual RAM" when physical memory is full.
    * Windows: Called **Paging**.
    * Linux: Called **Swap**.

## 2. File System Types
* **NTFS**: The default for Windows. Supports ACLs (permissions), encryption, and very large files.
* **FAT32**: Older, highly compatible with Windows, Linux, and Mac. 
    * **Limit**: Cannot store individual files larger than 4GB.
* **ext4**: The standard, high-performance file system for most Linux distributions.
* **APFS**: The modern file system used by Apple (macOS and iOS).

## 3. Windows Management
* **Disk Management Tool**: The primary GUI for initializing disks, creating partitions, formatting, and changing drive letters.
* **Disk Cleanup**: A built-in utility to remove temporary files and free up space.
* **Defragmentation**: Rearranges data on a physical hard drive (HDD) so files are stored in contiguous blocks, speeding up access. (Note: Not needed/recommended for SSDs).
* **chkdsk /f**: CLI command ("Check Disk") used to scan for and fix file system errors.

## 4. Linux Management (CLI)
* **lsblk**: "List Block Devices." Shows all connected drives and their partitions.
* **mount [device] [folder]**: Attaches a drive to a folder.
    * Example: `sudo mount /dev/sdb1 /mnt`
* **umount [folder]**: Detaches the drive. (Note: The command is `umount`, not "unmount").
* **df -h**: "Disk Free." Shows how much space is left on all mounted drives in human-readable format (GB/MB).
* **du -sh [directory]**: "Disk Usage." Shows the total size of a specific folder or file.
* **fsck**: "File System Check." The Linux version of chkdsk. Used to repair partitions (must be run while the drive is unmounted).

## 5. Troubleshooting
* **Low Disk Space**: Can cause "unusual errors" or system slowness.
* **Recommendations**: Use Cloud Storage for large media (photos/videos) to keep local storage free for apps and the OS.
