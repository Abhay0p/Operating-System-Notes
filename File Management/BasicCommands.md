### Basic Commands ( CLI and Linux )

## Navigation
* pwd: Print Working Directory. Shows current location in the file system.
* ls: List. Shows files and folders in the current directory.
    * Windows: ls -Force (shows hidden files).
    * Linux: ls -a (shows hidden files) or ls -l (long list with details).
* cd [path]: Change Directory. Moves to a specific location.
    * cd .. : Moves up to the parent directory.
    * cd ~ : Moves to the home directory.
    * cd . : Refers to the current directory.

## File and Directory Management
* mkdir [name]: Make Directory. Creates a new folder.
    * Use "quotes" for names with spaces: mkdir "my folder"
    * Use backticks for spaces in PowerShell: mkdir my` folder
* cp [source] [destination]: Copy.
    * Windows: cp -Recurse (to copy folders and contents).
    * Linux: cp -r (to copy folders and contents).
    * -Verbose: Shows a line-by-line output of what is being copied.
* mv [source] [destination]: Move or Rename.
    * To rename: mv old_name.txt new_name.txt
    * To move: mv file.txt /path/to/destination/
* rm [target]: Remove. Deletes files immediately.
    * Note: This does NOT use the Recycle Bin.
    * rm -Recurse (Windows) or rm -r (Linux): Deletes a folder and everything inside it.
    * -Force: Deletes protected or read-only files if permissions allow.

## Shortcuts and Patterns
* Tab: Auto-completes file or folder names.
* Asterisk (*): Wildcard for pattern matching (e.g., *.jpg for all image files).
* Up/Down Arrows: Cycles through command history.
* Ctrl + R: Searches through command history.
* clear: Clears the terminal screen of text.

## Getting Help
* Windows: Get-Help [command] -Full
* Linux: man [command] or [command] --help
