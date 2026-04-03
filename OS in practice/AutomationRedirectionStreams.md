# CLI Master Guide: Automation, Redirection, and Streams

## 1. I/O Streams (The "Water" Analogy)
Every process has three "pipes" or streams for data:
* **stdin (Standard In)**: Data flowing INTO the program (Keyboard).
* **stdout (Standard Out)**: Data flowing OUT of the program (Screen).
* **stderr (Standard Error)**: Error messages flowing out (Separate from normal data).

## 2. Redirector Operators
Use these to change where data goes.
* **`>` (Overwrite)**: Sends stdout to a file, deleting whatever was there before.
    * Example: `echo "hello" > file.txt`
* **`>>` (Append)**: Sends stdout to the end of a file without deleting contents.
    * Example: `echo "world" >> file.txt`
* **`<` (Standard In)**: Uses a file as the input for a command instead of the keyboard.
* **`2>` (Error Redirection)**: Sends only the error messages to a specific file.
    * Example: `rm protected_file 2> errors.txt`

## 3. The "Black Hole" (Filtering Errors)
If you want to run a command and hide the errors entirely:
* **Windows**: Redirect to `$null` (e.g., `command 2> $null`)
* **Linux**: Redirect to `/dev/null` (e.g., `command 2> /dev/null`)

## 4. Pipes (`|`)
The pipe takes the **stdout** of one command and makes it the **stdin** for the next. This allows you to chain small tools to do big tasks.
* **Search inside a list**: `ls | grep "target"` (Linux) or `ls | sls "target"` (Windows).
* **Count files**: `ls | wc -l` (Linux).

## 5. Advanced Search & Filtering
* **grep (Linux)**: Search for text inside files or streams.
    * `-r`: Recursive search.
    * `-w`: Whole word only.
* **sls / Select-String (Windows)**: The PowerShell version of grep.
* **ls -Filter (Windows)**: Quickly find specific file types.
    * Example: `ls -Recurse -Filter *.exe` (Finds all executables).

## 6. CLI Power User Tips
* **Syntax Highlighting**: Editors like Notepad++ or Nano use colors to help you read code/config files easily.
* **History Search (Ctrl + R)**: Search your "brain" (the shell's memory) for that one long command you typed yesterday.
* **Tab Completion**: The #1 skill. Never type a full filename; type the first two letters and hit Tab.
* **Echo**: Used to print text to the screen or to quickly create a file using redirection.
