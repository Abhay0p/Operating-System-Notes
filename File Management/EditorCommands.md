# CLI Reference: Viewing, Editing, and Searching

## 1. Viewing File Contents
* **cat [file]**: Short for concatenate. Dumps the entire file content into the terminal.
* **more [file]** (Windows/Linux): Views file one page at a time.
    * Enter: Advance by one line.
    * Space: Advance by one page.
    * q: Quit and return to shell.
* **less [file]** (Linux): More powerful than "more."
    * Up/Down/PageUp/PageDown: Navigate freely.
    * g: Move to start of file.
    * G: Move to end of file.
    * /[word]: Search for a specific word within the file.
    * q: Quit.
* **head [file]**: Shows the first 10 lines of a file by default.
    * Windows: `cat [file] -Head 10`
* **tail [file]**: Shows the last 10 lines of a file by default.
    * Windows: `cat [file] -Tail 10`

## 2. Editing Files (Linux)
* **nano [file]**: A lightweight CLI text editor.
    * Ctrl + G: Open help.
    * Ctrl + O: Write out (Save).
    * Ctrl + X: Exit (will prompt to save if changes were made).

## 3. Searching for Text (Strings)
* **sls** (Select-String): The PowerShell command to find text patterns in files.
    * Example: `sls "word" file.txt`
    * Using Wildcards: `sls "word" *.txt` (searches all text files in the directory).
* **grep** (Linux): The standard tool for searching text in files (similar to sls).

## 4. PowerShell Concepts
* **Get-Alias [alias]**: Shows the real PowerShell command behind a shortcut.
    * Example: `Get-Alias ls` reveals it points to `Get-ChildItem`.
* **Standard Commands**:
    * PowerShell: Use `Get-Help [command]`
    * Old CMD/MS-DOS: Use `[command] /?` (Note: These don't always mix).
* **Strings**: How computers represent text data.

## 5. Windows GUI Tips
* **Properties > Open With**: Change the default app (like moving from Notepad to WordPad).
* **Indexing Options**: Used to enable "File Contents" searching in the Windows Search Service (Start > Indexing Options > Advanced > File Types).
* **Notepad++**: Use `Ctrl + Shift + F` to find a string across multiple files in a directory.
