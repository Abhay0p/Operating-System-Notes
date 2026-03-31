# CLI & GUI Reference: Advanced Permissions and Security

## 1. Key Concepts: Advanced Access
* **Simple Permissions**: Sets of "pre-packaged" permissions (Read, Write, Modify) used for most daily tasks.
* **Special Permissions**: Granular, fine-tuned permissions that make up the simple sets (e.g., "Append Data" or "Read Attributes").
* **Deny vs. Allow**: In Windows, an explicit "Deny" almost always overrides an "Allow."
* **Authenticated Users**: A Windows group that includes anyone with a valid account and password on the system (excludes Guest accounts).

## 2. Advanced Windows Permissions (icacls)
* **DACL (Discretionary ACL)**: Defines who can use a file and what they can do.
* **SACL (System ACL)**: Used for auditing; it logs an event every time a file is accessed.
* **Inheritance Flags**:
    * **(OI) Object Inherit**: Files created in this folder will inherit the DACL.
    * **(CI) Container Inherit**: Subfolders created here will inherit the DACL.
    * **(IO) Inherit Only**: The permission applies to children/sub-items, but not to the folder itself.
* **Specific Permission Codes**:
    * **F**: Full Access
    * **M**: Modify Access
    * **RX**: Read and Execute
    * **R**: Read-only
    * **WD**: Write Data / Create Files
    * **AD**: Append Data / Create Folders

### Command Examples (PowerShell)
* `icacls 'C:\Folder' /grant 'Everyone:(OI)(CI)(R)'` : Give everyone read access to folder and all future contents.
* `icacls 'C:\Folder' /remove Everyone` : Completely remove the "Everyone" group from the ACL.

## 3. Advanced Linux Permissions (Special Bits)
Linux uses three special bits that sit "on top" of the standard rwx:

* **setuid (Value: 4)**: The file runs with the permissions of the **owner**.
    * *Example*: The `passwd` command has this so a normal user can write to the root-owned `/etc/shadow` file to change their own password.
    * Represented by an **s** in the owner's execute slot: `-rws------`
* **setgid (Value: 2)**: The file runs with the permissions of the **group**.
    * Represented by an **s** in the group's execute slot: `----rws---`
* **Sticky Bit (Value: 1)**: Anyone can write/edit files in the folder, but **only the owner or root** can delete them.
    * *Example*: The `/tmp` directory.
    * Represented by a **t** at the very end: `drwxrwxrwt`

### Command Examples
* `chmod +t my_folder` : Enable the sticky bit symbolically.
* `chmod 1755 my_folder` : Enable sticky bit (1) with standard rwx (755) permissions.
* `chmod 4755 my_script` : Enable setuid (4) on a script.

## 4. Master Glossary: Security & Identity
* **Computer Management**: The central Windows tool for managing users, disks, and services.
* **Root User / Superuser**: The all-powerful Linux account (UID 0).
* **SSO (Single Sign On)**: One account/password to access multiple different systems.
* **MDM (Mobile Device Management)**: Systems used to enforce security policies on phones and laptops.
* **Biometric Data**: Using physical traits (fingerprints, face) for authentication.
* **I/O Streams**:
    * **stdin**: Input into a program (keyboard).
    * **stdout**: Normal output (screen).
    * **stderr**: Error messages (separate stream).
* **Redirectors**:
    * `>` : Overwrite file with output.
    * `>>` : Append output to the end of a file (don't erase existing data).
