# CLI & GUI Reference: Process Management

## 1. Key Concepts
* **Program vs. Process**: A program is a file on your disk; a process is a program that is currently running in the RAM.
* **PID (Process ID)**: A unique number assigned by the OS to every running process to keep track of it.
* **Multitasking**: The OS manages many processes at once by switching between them extremely fast.
* **Signals**: Notifications sent to a process to tell it to stop, restart, or pause.
* **Resource Monitoring**: Tracking how much CPU (Processing power) and RAM (Memory) each process uses.

## 2. Windows Management (GUI & CLI)
* **Task Manager (Ctrl+Shift+Esc)**: The primary GUI tool to view active processes and "End Task" on frozen ones.
* **Resource Monitor**: A detailed version of Task Manager for granular disk and network activity.
* **Get-Process**: PowerShell commandlet to list all active processes on the system.
* **Stop-Process -ID [PID]**: Forcefully kills a process using its unique ID number.
* **Stop-Process -Name "ProgramName"**: Kills all processes with that specific name.

## 3. Linux Management (CLI)
* **ps**: "Process Status." Shows a snapshot of current processes.
    * `ps aux`: Shows every process running on the system for all users.
* **top**: A real-time, interactive list of processes (like a CLI Task Manager).
* **kill [PID]**: Sends a signal to a process to stop it.
    * `kill -9 [PID]`: The "Force Kill" signal that stops a process immediately without saving data.
* **& (Ampersand)**: Adding an `&` to the end of a command runs it in the "background" so you can keep using the terminal.
    * Example: `cp -r /large_folder /backup &`
* **jobs**: Lists the processes currently running in the background of your shell.
* **fg [job_id]**: "Foreground" - brings a background job back to the front of your terminal.

## 4. Troubleshooting
* **Zombie Process**: A process that has finished running but still has an entry in the system table (it's "dead" but hasn't disappeared).
* **Memory Leak**: When a program fails to release RAM it is no longer using, eventually slowing down or crashing the system.
* **CPU Saturation**: When a process takes up 100% of the CPU, making the rest of the computer unresponsive.
