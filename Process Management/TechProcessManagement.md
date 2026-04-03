# Module 5: Process Management

## 1. Key Concepts & Definitions
* **Program vs. Process**: A program is a set of instructions stored on your disk (like an `.exe`); a process is an instance of that program currently executing in the RAM.
* **PID (Process ID)**: A unique identification number assigned by the OS to every running process.
* **Time Slicing**: The technique the OS uses to switch between processes so quickly that it appears they are running at the same time (Multitasking).
* **Resource Monitoring**: The practice of tracking CPU usage (processing power) and RAM (memory) to ensure system health.

## 2. Windows Management (GUI & CLI)
* **Task Manager (Ctrl+Shift+Esc)**: The go-to GUI tool for viewing active processes, resource usage, and "Ending Tasks" on unresponsive programs.
* **Resource Monitor**: An advanced tool for granular data on Disk and Network activity per process.
* **Get-Process**: PowerShell commandlet to list all active processes.
* **Stop-Process -ID [PID]**: Forcefully kills a process using its unique ID.
* **Stop-Process -Name "ProgramName"**: Kills all active instances of a specific program.

## 3. Linux Management (CLI)
* **ps**: "Process Status." 
    * `ps aux`: The most common way to see every process running on the system for all users.
* **top**: A real-time, interactive monitor (CLI version of Task Manager).
* **Signals (The 'Kill' Logic)**:
    * **SIGTERM (15)**: The "polite" signal. Asks the program to save data and close normally.
    * **SIGKILL (9)**: The "hammer." Instantly terminates the process without saving (`kill -9 [PID]`).
    * **SIGHUP (1)**: "Hang Up." Often used to tell a program to reload its configuration files without a full restart.
* **Background & Foreground**:
    * **& (Ampersand)**: Run a command in the background (e.g., `command &`).
    * **jobs**: Lists processes running in the background of your current shell.
    * **Ctrl + Z**: Pauses a foreground process and moves it to the background.
    * **bg [job_id]**: Restarts a paused background job.
    * **fg [job_id]**: Brings a background job back to the foreground.

## 4. Troubleshooting Processes
* **Zombie Process**: A process that has finished executing but remains in the process table because its parent hasn't "reaped" it. It consumes no resources but holds a PID.
* **Memory Leak**: A bug where a program forgets to release RAM it no longer needs. Over time, this "leaked" memory causes the system to run out of RAM and crash.
* **CPU Saturation**: When a process (or "runaway process") hits 100% CPU usage, making the computer laggy or unresponsive.
* **Orphan Process**: A child process whose parent has finished or terminated, leaving it to be adopted by the `init` (PID 1) process.
