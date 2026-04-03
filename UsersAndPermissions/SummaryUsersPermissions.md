# Module 2: User, Group, and Permission Management

## 1. Key Concepts & Identity Basics
* **Standard User**: Has restricted access. They can use the machine but cannot install software or change system-wide settings.
* **Administrator (Admin)**: Has full, "unfettered" control over the machine. They can manage all accounts and view any file.
* **The Root User**: In Linux, this is the "Superuser" (UID 0). It is the first account created and has absolute power over the OS.
* **User Isolation**: By default, users are isolated. One user cannot see another's files unless they use a "Shared Folder."
* **Windows Domain**: A network of computers and users managed via a central database.
* **Active Directory (AD)**: The service used by IT to manage thousands of users and their permissions from one central point.
* **MDM (Mobile Device Management)**: Systems used to apply and enforce security rules on mobile devices (phones/laptops).

## 2. Security Best Practices
* **Principle of Least Privilege**: Best practice is to log in as a standard user and only use admin powers when absolutely necessary to avoid system-wide mistakes or malware.
* **UAC (User Account Control)**: A Windows security feature that prompts for an admin password/approval before allowing a system change.
* **Sudo (Superuser Do)**: A Linux command that allows a normal user to run a single task with root privileges.
* **Hashing vs. Encryption**: Passwords (like in Linux `/etc/shadow`) are **hashed** (a one-way scramble) so they can be verified but never "unlocked" or read.
* **Password Privacy**: Never type a password directly into a command line (it stays in logs). 
    * **Pro-Tip**: Use the asterisk `*` in commands to be prompted for a hidden password.

## 3. Windows User Management (GUI & CLI)
* **Computer Management Tool**: The central hub for local administration (Local Users and Groups).
* **Account Flags**:
    * **Disabled/Locked Out**: The account is inactive or the user is barred from logging in.
    * **User must change password at next login**: A security best practice when an admin sets a temporary password.
* **CLI Commands (PowerShell)**:
    * `Get-LocalUser`: Lists all local accounts and their status.
    * `Get-LocalGroupMember [Group]`: Shows who is in a specific group (e.g., "Administrators").
    * `net user [name] * /add`: Creates a new user and prompts for a secure password.
    * `net user [name] /delete`: Removes the user account.
    * `net user [name] /logonpasswordchg:yes`: Forces a password change at the next login.

## 4. Linux User Management (CLI & Files)
* **System Files (Source of Truth)**:
    * **/etc/passwd**: Stores usernames, UIDs (User IDs), and shell info.
    * **/etc/shadow**: A highly protected file that stores the hashed passwords.
    * **/etc/group**: Stores group names, GIDs (Group IDs), and member lists.
* **CLI Commands**:
    * `su - [user]`: Substitute User. Switches the session to another user (defaults to root).
    * `useradd [name]`: Creates a new user account.
    * `userdel [name]`: Deletes a user account.
    * `passwd [name]`: Changes a password.
    * `passwd -e [name]`: Immediately expires the password to force a change at next login.

## 5. Windows Permissions (NTFS & ACLs)
* **ACL (Access Control List)**: The list of permissions attached to a file or folder.
    * **DACL (Discretionary)**: Defines who can use a file and what they can do.
    * **SACL (System)**: Used for auditing; logs an event every time a file is accessed.
* **Permission Levels**: Read, Read & Execute (List Folder Contents), Write, Modify (Umbrella), and Full Control.
* **Deny vs. Allow**: An explicit **Deny** always overrides an **Allow**.
* **Inheritance Flags**:
    * **(OI) Object Inherit**: Files in this folder will inherit the DACL.
    * **(CI) Container Inherit**: Subfolders in this folder will inherit the DACL.
    * **(IO) Inherit Only**: Permission applies to children, but not the parent itself.
* **icacls Command**:
    * `icacls 'C:\Path' /grant 'User:(OI)(CI)(R)'`: Grant Read access with inheritance.
    * `icacls [path] /remove [User]`: Completely remove a user from the ACL.

## 6. Linux Permissions (10-Bit System)
* **Structure**: `[Type][Owner][Group][Others]` (e.g., `-rwxrw-r--`)
    * **Type**: `d` = directory, `-` = file.
* **The Values**: **4** (Read), **2** (Write), **1** (Execute).
* **Numeric Mode**: `chmod 755 [file]` (Owner: 7/rwx, Group: 5/r-x, Others: 5/r-x).
* **Special Bits**:
    * **setuid (Value: 4)**: File runs with owner (root) privileges. Shown as `s` in owner slot.
    * **setgid (Value: 2)**: File runs with group privileges. Shown as `s` in group slot.
    * **Sticky Bit (Value: 1)**: Anyone can write, but only the owner can delete. Shown as `t` at the end.
* **Ownership**:
    * `chown [user] [file]`: Change the owner of a file.
    * `chgrp [group] [file]`: Change the group ownership.

## 7. Identity & Glossary
* **SSO (Single Sign-On)**: One account/password to access multiple different systems.
* **Biometric Data**: Authentication using unique physical traits (Fingerprint, Face).
* **Authenticated Users**: A Windows group including everyone with a valid account (excludes Guests).
