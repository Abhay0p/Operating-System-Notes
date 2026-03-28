# Linux File Management: Lab Reference

## 1. System Basics
* File names are **case-sensitive** (e.g., `File.txt` and `file.txt` are different).
* Special characters (spaces, brackets) must be **escaped** with a backslash `\` (e.g., `Europe\ Pictures`).
* **.** (dot) represents the current directory.

## 2. Navigation and Viewing
* **ls**: List directory contents.
    * `ls -l`: Shows long format (permissions, ownership, size).
    * `ls -a`: Shows all files, including hidden ones (files starting with a dot).
* **pwd**: Print Working Directory. Shows your full path from the root `/`.
* **cd [path]**: Change directory. 
* **cat [path/file]**: Dumps the entire contents of a file to the screen.
* **less [path/file]**: Opens a scrollable view for large files.
    * `Enter`: Scroll down one line.
    * `q`: Exit/Quit the view.

## 3. Creating and Deleting
* **mkdir [name]**: Create a new directory.
    * `mkdir dir1 dir2`: Create multiple directories at once.
    * `-p`: Create parent directories if they don't exist.
    * `-v`: Verbose mode (shows a message for each directory created).
* **touch [name]**: Creates a new empty file or updates the timestamp of an existing one.
    * `-c`: Do not create a new file if it doesn't already exist.
* **rmdir [name]**: Removes an **empty** directory.
    * `-p`: Removes parent directories if they become empty after the child is deleted.
* **rm [file]**: Removes files.
    * `rm -r [directory]`: Recursively removes a directory and all its contents (required for non-empty folders).

## 4. Moving and Copying
* **cp [source] [target]**: Copies files or directories.
    * If target is a directory, the file is copied into it.
    * If target file exists, it will be overwritten.
* **mv [source] [target]**: Moves or renames files/directories.
    * Use `mv [file] .` to move a file from another location into your current folder.

## 5. Searching with Grep
* **grep [options] -e "pattern" [path]**: Searches for text within files.
    * `-r`: Search recursively through subdirectories.
    * `-w`: Match the whole word only.
    * `-n`: Show the line number where the match was found.
    * `--exclude-dir=[name]`: Skip specific directories in the search.

## 6. Text Editing (Nano)
* **nano [file]**: Opens the editor.
* **Ctrl + O**: "Write Out" (Save the file). Must hit `Enter` to confirm the filename.
* **Ctrl + X**: Exit the editor.
* **Ctrl + G**: Get help/See shortcuts.
