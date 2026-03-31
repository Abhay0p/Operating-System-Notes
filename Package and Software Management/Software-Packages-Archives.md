# CLI & GUI Reference: Software Packages and Archives

## 1. Software Packaging Basics
* **The Concept**: Developers "package" software like a gift. You might put it in a box or a bag, but the contents are what matter.
* **Executable (.exe)**: A file in Windows that contains instructions for the computer to run, like "copy this file" or "install this program."
* **MSI File**: A "Microsoft Install" package used to guide the Windows Installer. It handles the installation, maintenance, and removal of programs.
* **APPX**: A unit of distribution for "Universal Windows Platform" apps that run on PCs or tablets.

## 2. Windows Installation (GUI vs. CLI)
* **GUI**: Usually just a double-click on the `.exe` to start a setup wizard.
* **CLI (Command Line)**: Helpful for "automatic installations" where you don't want a human clicking buttons.
    * Use the **absolute path** to run an installer (e.g., `C:\Users\Cindy\Desktop\hello.exe`).
    * **/quiet**: Silent installation (nothing shows on screen).
    * **/norestart**: Prevents the computer from rebooting automatically.
    * **/extract:[path]**: Unpacks the contents to a specific folder.
    * **/?**: The "Pro Tip" parameter to see what sub-commands an installer supports.

## 3. Linux Packages (Debian focus)
* **Distros**: Different Linux distributions use different types. Red Hat uses **.RPM**, while Ubuntu uses **.deb** (Debian).
* **dpkg (Debian Package)**: The standalone command to manage these.
    * `sudo dpkg -i [package_name]`: Install the package.
    * `sudo dpkg -r [package_name]`: Remove the package.
    * `dpkg -l`: List all installed packages.
    * **Piping to Grep**: Use `dpkg -l | grep [name]` to find if a specific package is installed.

## 4. Dependencies and Libraries
* **Dependency**: When one piece of software "depends" on another to work (e.g., a game needing a physics engine).
* **Library**: A bundle of useful code someone else wrote that programs can "tap into."
* **DLL (Dynamic Link Library)**: Windows shared libraries.
* **DLL Hell**: An old problem where a new app updates a DLL and breaks an old app.
* **WinSxS (Side-by-Side)**: The modern fix. It stores multiple versions of the same library in `C:\Windows\WinSxS` so programs don't "pull the rug out" from each other.
* **Manifest**: An XML file that tells Windows exactly which version of a library a program needs.

## 5. Modern Package Managers
* **The Goal**: To make installation easier by automatically installing "dependencies" for you.
* **Chocolatey**: A "repository" (warehouse) where Windows software lives.
* **Find-Package**: A PowerShell commandlet to locate software.
* **Install-Package**: The command to actually download and set up the software.

## 6. Archives and Compression
* **Archive**: One or more files "squished" into a single file to save space or send in an email. (Types: `.zip`, `.tar`, `.rar`).
* **7-Zip**: A popular tool for extracting (un-archiving) these files.
    * Windows GUI: Right-click > 7-Zip > Extract Here.
    * Linux CLI: `7z e [file_name]`.
* **PowerShell**: Use `Compress-Archive` to turn a folder into a `.zip` file from the command line.

## 7. Mobile App Management
* **App Stores**: Central, managed marketplaces where apps are reviewed for security.
* **Code Signing**: A digital "signature." If someone changes the code, the signature becomes invalid, and the OS knows the code was "tampered with."
* **Sideloading**: Installing an app directly (like an APK) without an app store. This is risky.
* **Enterprise Management**: Using **MDM** (Mobile Device Management) to push custom, private apps to employee devices.
* **Cache**: The assigned storage location for an app's data. Clearing the cache is a simple way to "reset" an app.
