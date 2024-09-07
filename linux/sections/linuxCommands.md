> # Basic Commands

### `which` command:

The which command in Linux is used to locate the executable file associated with a given command by searching the directories listed in the user's PATH environment variable.

```shell
which commandName
```

### `history` command:

The history command displays a list of previously executed commands in the current shell session, providing a chronological record of commands for reference or reuse

```shell
history
```

### `--help` command:

The commandName --help command displays a summary of usage information and available options for the specified command, helping users understand how to use it

```shell
commandName --help
```

### `type` command:

The type command displays all locations and types (e.g., alias, function, executable file) of the specified command within the current shell session.

```shell
type -a commandName
```

### `man` command:

The man command in Linux is used to display the manual pages for other commands and programs, providing detailed information and usage instructions.

```shell
man ofCommand(like ls and rm)
```

### `pwd` command:

The pwd command prints the absolute path of the current working directory in the terminal.

```shell
pwd
```

### `cd` command:

The cd command in Linux is used to change the current working directory

- The cd . command changes the current directory to itself, effectively doing nothing and leaving you in the same directory.
  ```shell
  cd .
  ```
- The cd .. command changes the current directory to the parent directory of the current location.

  ```shell
  cd ..
  ```

- The cd path command changes the current directory to the specified path, which can be either an absolute or relative path to a directory.

  ```shell
  cd path
  ```

- The cd ~ or simply cd command changes the current directory to the user's home directory.

  ```shell
  cd ~
  cd
  ```

### `ls` command:

Lists the files and directories in the current directory.

- Provides a detailed listing of files and directories, including permissions, number of links, owner, group, size, and timestamp.

  ```shell
  ls -l
  ```

- Lists all files, including hidden files (those starting with a dot .)

  ```shell
  ls -a
  ```

- The -F option with ls appends a character to each file name indicating its type: / for directories, \* for executables, @ for symbolic links, and | for FIFOs (named pipes).

  ```shell
  ls -F
  ```

- The -i option in the ls command is used to display the inode number of each file. The inode number is a unique identifier for each file within a file system

  ```shell
  ls -i
  ```

- Combines detailed listing with hidden files.

  ```shell
  ls -la or ls -al
  ```

### `echo` command:

The echo command in Linux is used to display a line of text or a variable's value to the terminal.

```shell
echo "hello world"
```

### `mkdir` command:

The mkdir command in Linux is used to create new directories.

```shell
mkdir nameOfDirectory
```

### `touch` command:

The touch command in Linux is used to create empty files or update the access and modification timestamps of existing files.

```shell
touch
```

### `rm` command:

The rm command in Linux is used to remove files or directories

- The rm fileName command deletes the file named fileName without prompting for confirmation

  ```shell
  rm nameOfFile
  ```

- The rm -r dirName command recursively deletes the directory dirName and all its contents, including subdirectories and files, without prompting for confirmation

  ```shell
  rm -r dirName
  ```

### `rmdir` command:

The rmdir dirName command removes the empty directory named dirName

```shell
rmdir dirName
```

### `cat` command:

The cat command in Linux is used to concatenate and display the contents of files.

```shell
cat nameOfFile
```

### `cp` command

The cp (copy) command in Linux is used to copy files and directories from one location to another.

- `-r` or `--recursive`: Copy directories recursively, including all files and subdirectories.

- `-v`or `--verbose`: Display detailed information about what is being copied.

```s
cp -r -v source_directory/ destination_directory/
```
### `mv` command

The mv command in Linux is used to move or rename files and directories

```s
mv file1.txt /destination/
```