# CLI & GUI Reference: Advanced Software Management

## 1. Shared Libraries & DLL Troubleshooting
* **The Concept**: Shared libraries (DLLs in Windows, .so in Linux) allow multiple programs to use the same code. This saves RAM because the code is only loaded once.
* **Side-by-Side (SxS) Assemblies**: Windows stores multiple versions of the same DLL in `C:\Windows\WinSxS`. This prevents "DLL Hell" (where one app breaks another by updating a shared file).
* **Manifests**: XML files that tell the OS exactly which version of a library a specific program needs to run.

## 2. Device Drivers
* **Definition**: Small pieces of software that allow the OS to talk to hardware (printers, GPUs, etc.).
* **Windows Device Manager**: The tool to update, roll back, or disable drivers.
* **Linux Drivers**: Usually "baked into" the Kernel. If hardware isn't working, you may need to install a "Kernel Module."

## 3. Windows CLI: The 'Net' Command
* **net start [service]**: Starts a system service (like a print spooler).
* **net stop [service]**: Stops it. This is a common troubleshooting step for "stuck" software.
