# CLI & GUI Reference: User and Group Management

## 1. Key Concepts & Best Practices
* **Standard User vs. Admin**: Standard users have restricted access to prevent accidental malware installation or system damage. Administrators (Admins) have "unfettered" or complete control.
* **The Root User**: In Linux, this is the "Superuser" (UID 0). It is the first account created and has absolute power over the OS.
* **Isolation**: By default, users are isolated. One user cannot see another's files unless they use a "Shared Folder."
* **UAC & Sudo**: Windows (User Account Control) and Linux (Superuser Do) both use these features to allow a normal user to perform admin tasks only when authorized by a password or prompt.
* **Hashing vs. Encryption**: Passwords (especially in Linux `/etc/shadow`) are **hashed** (a one-way scramble) so they can be verified but never "unlocked" or read by others.
* **Least Privilege**: Best practice is to log in as a standard user and only use admin powers when absolutely necessary to avoid system-wide mistakes.
* **Password Privacy**: Never type a password directly into a command line (it stays in logs). Always use shortcuts like the asterisk `*` to be prompted securely.

## 2. Windows Management (GUI)
* **Computer Management Tool**: The central hub for local administration.
    * **Local Users and Groups**: Where you create, delete, and manage account properties.
    * **Event Viewer**: Where system logs are stored.
    * **Task Scheduler**: Used to automate programs (e.g., auto-shutdown at 11 PM).
* **Account Flags**:
    * **Disabled/Locked Out**: The account is inactive or the user is barred from logging in.
    * **User must change password at next login**: A security best practice when an admin sets a temporary password.

## 3. Windows User Management (CLI)
* **Get-LocalUser**: Lists all local accounts and shows if the Admin account is enabled.
* **Get-LocalGroupMember [Group]**: Shows who is in a specific group (e.g., "Administrators").
* **net user [name] * /add**: Creates a new user and prompts for a secure password.
* **net user [name] /delete**: Removes the user account.
* **net user [name] /logonpasswordchg:yes**: Forces a password change at the next login.

## 4. Linux User Management (CLI)
* **su (Substitute User)**: Switches to another user (defaults to root). Use `exit` to go back.
* **sudo**: Runs a single command with root privileges. 
* **useradd [name]**: Creates a new user account.
* **userdel [name]**: Deletes a user account.
* **passwd [name]**: Changes a password. 
    * `passwd -e [name]`: Immediately expires the password to force a change.

## 5. Linux System Files
* **/etc/passwd**: Stores usernames, UIDs (User IDs), and basic info.
* **/etc/shadow**: A highly protected file that stores the hashed passwords.
* **/etc/group**: Stores group names, GIDs (Group IDs), and lists of members.
    * Example: `sudo:x:27:cindy` (Group: sudo, Password: encrypted, GID: 27, User: cindy).

## 6. Enterprise Environment
* **Windows Domain**: A network of computers and users managed via a central database.
* **Active Directory**: The service used to manage thousands of users across an organization from one central point.
