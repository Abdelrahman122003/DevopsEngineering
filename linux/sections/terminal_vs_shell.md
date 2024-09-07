# Terminal Vs Shell

A `shell` is a command-line interpreter that provides a user interface for interacting with the operating system. It allows users to execute commands, run programs, and automate tasks using scripts. Examples include Bash, Zsh, and PowerShell.

A `terminal` (or terminal emulator) is a software application that provides a text-based interface to interact with the shell. It displays the shell's output and allows users to input commands. Examples include GNOME Terminal, Windows Terminal, and iTerm2.


# Shell Expansion

Shell expansion is a process in Unix-like operating systems where the shell interprets and transforms certain types of characters or expressions before executing a command.

- `Variable Expansion`: Replaces variables with their values.
  ```s
  echo $HOME
  ```
- `Command Substitution`: Executes a command and replaces it with its output
  ```s
  echo "Today is ${DATE}"
  ```
- `Pathname Expansion (Globbing)`: Expands wildcard characters (*, ?, and []) to match filenames.
  ```s
  ls *.txt
  ```
- `Arithmetic Expansion`: Allows arithmetic operations within double parentheses (( )).
  ```s
  echo $((3 + 5))
  ```
- `Brace Expansion`: Generates sequences of strings. Useful for creating multiple files or directories with similar names.
  ```s
  mkdir project_{1..5}
  ```
- `Tilde Expansion`: Replaces the tilde (~) with the user's home directory.
  ```s
  cd ~
  ```

# Environment variable

Environment variables are dynamic values that can affect the behavior of processes on a computer. They are used to configure system-wide or application-specific settings without hardcoding them into the software.


Variables created in the terminal are typically not saved permanently. They are set only for the current session or until the terminal window is closed.

- `export` command
  
  The export command is used to set an environment variable and make it available to child processes.

    ```s
    export <var-name>
    ```
- `declare -x` command
  
  - The declare -x command is used to declare and export variables in one step, making them available as environment variables
  
    ```s
    declare -x name=value
    ```
  - This command will output a list of all environment variables that are exported, showing their names and values.
  
    ```s
    declare -x
    ```