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