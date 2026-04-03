# Module 1: OS Architecture, Navigation, and File Management

## 1. OS Architecture & Theory
* **Kernel vs. User Space**: 
    * **Kernel**: The "heart" of the OS. It talks directly to hardware (CPU, RAM, Storage). Users do not interact with this directly.
    * **User Space**: Where users and applications (Web browsers, shells, GUI) live.
* **File System**: The specific method the OS uses to keep track of data bits on a disk so they can be retrieved as organized files and folders.
* **Case Sensitivity**: Linux file names are **case-sensitive** (`File.txt` vs `file.txt`). Windows is generally case-insensitive.

## 2. File System Hierarchy & Paths
* **Root Directory**: The base of the directory tree.
    * **Windows**: Assigned to drive letters (e.g., `C:\`).
    * **Linux**: Denoted by a forward slash (`/`). There are no drive letters.
* **Path Types**:
    * **Absolute**: Starts from the main/root directory. Works from anywhere.
    * **Relative**: Starts from your current directory.
* **Shortcuts**:
    * `.` (Dot): Current directory.
    * `..` (Double Dot): Parent directory (one level up).
    * `~` (Tilde): Home directory (`C:\Users\Name` or `/home/name`).

## 3. Navigation & Viewing Commands
| Command | Description | Notes |
| :--- | :--- | :--- |
| **pwd** | Print Working Directory | Shows current location. |
| **ls** | List | Shows files/folders. Win: `ls -Force` (hidden). Linux: `ls -la` (all/long). |
| **cd [path]** | Change Directory | Move between folders. |
| **cat [file]** | Concatenate | Dumps entire file content to terminal. |
| **more [file]** | Page viewer | Advance with `Space`, line-by-line with `Enter`, quit with `q`. |
| **less [file]** | Advanced viewer | (Linux) Supports searching with `/` and scrolling. |
| **head/tail** | View start/end | Shows first or last 10 lines of a file. |

## 4. File and Directory Management
* **mkdir [name]**: Creates a folder.
    * *Handling Spaces*: Wrap in `"Quotes"`. 
    * *Escape Characters*: Linux uses `\`. PowerShell uses the **backtick ( ` )**.
* **cp [src] [dest]**: Copies files.
    * **Recursive**: Required for folders. Win: `cp -Recurse`. Linux: `cp -r`.
    * **-Verbose**: Shows a line-by-line output of the copy process.
* **mv [src] [dest]**: Moves or renames.
* **rm [target]**: Removes files. **Warning**: No Recycle Bin; deletion is permanent.
    * **rm -r**: Deletes a folder and everything inside.
    * **-Force**: Overrides protection for read-only or system files.
* **touch [file]**: (Linux) Creates an empty file or updates timestamps.

## 5. Searching and Text Manipulation
* **sls / Select-String**: (Windows) Finds text patterns in files.
* **grep**: (Linux) Finds text patterns in files. Use `-r` for recursive search.
* **Wildcard (*)**: Matches any pattern (e.g., `*.jpg`).
* **ls -Filter**: (Windows) `ls -Filter *.exe -Recurse` finds all executables in a tree.

## 6. I/O Streams and Redirection
* **The Three Streams**:
    1. **stdin**: Input (Keyboard).
    2. **stdout**: Normal Output (Screen).
    3. **stderr**: Error messages.
* **Operators**:
    * `>` : Overwrites a file with output.
    * `>>` : Appends output to the end of a file.
    * `2>` : Redirects only the error stream (e.g., `command 2> errors.txt`).
    * **Black Holes**: Hide errors by sending to `$null` (Win) or `/dev/null` (Linux).
* **Pipes (|)**: Sends the **stdout** of one command to the **stdin** of the next (e.g., `ls | grep "text"`).

## 7. Troubleshooting & GUI Tips
* **Tab Completion**: Hit `Tab` to auto-complete names.
* **History Search**: `Ctrl + R` to search previous commands. 
* **Properties (Windows)**:
    * **Size on Disk**: Actual physical space occupied (usually larger than data size).
    * **Restore Previous Versions**: Reverts changes if System Protection is enabled.
* **Get-Alias**: (Windows) Shows the real command behind a nickname (e.g., `ls` is actually `Get-ChildItem`).

## 8. Glossary Quick-Ref
* **CLI**: Command Line Interpreter.
* **Shell**: The CLI for Linux (e.g., Bash).
* **Hot Key**: Keyboard shortcut (e.g., `Ctrl+Shift+Esc` for Task Manager).
* **GUI**: Graphical User Interface.
* **Windows Search Service**: Indexes files for faster searching (Configure via Indexing Options).
