# data streams

## Standard Streams (Data Transported from Terminal to Shell or Vice Versa)

- Standard input (from terminal to shell) -> STDIN -> INDEX 0
  Anything you write in the terminal, separated by spaces, is called a token.
  like this command :

  ```shell
  # This Command Calls Standard Input
  ls(token) -l(token) ~(token)
  ```

- Standard output (from shell to terminal) -> STDOUT -> INDEX 1

  ```shell
  # This Command Calls Standard Output
  # total 8
  # -rw-rw-r-- 1 zoombie zoombie   27 Jun 27 10:04 file.txt
  # -rw-rw-r-- 1 zoombie zoombie    0 Jun 27 10:03 main.cpp
  # drwxrwxr-x 2 zoombie zoombie 4096 Jun 27 10:03 myFolder
  ```

- Standard error (from shell to terminal) -> STDERR -> INDEX 2

> ### Redirection

<!-- ouput -->

- `>`: Redirects the standard output (stdout) of a command to a file, overwriting the file if it already exists.

  ```shell
  ls -l ~ > fileName.txt
  ```

- `>>`: Appends the standard output of a command to the end of a file without overwriting it.

  ```shell
  ls -l ~ >> fileName.txt
  ```

- `2>`: Redirects the standard error (stderr) output of a command to a file, overwriting the file if it already exists.

  ```shell
  # 2 refer to Index as explained above
  ls non_existing_file 2> error.txt
  ```

- `2>>`: Appends the standard error of a command to a file without overwriting it.

  ```shell
  ls non_existing_file 2>> error.txt
  ```

- `>&`: Redirects both stdout and stderr to the same file.

  ```shell
  cat /etc/shadow >& outputMix
  ```

- `|`: Pipes the output of one command to another command as input.

  ```shell
  ls | grep "pattern
  ```

<!-- input -->

- `<`:

  ```shell
  cat < in.txt
  ```

> ## Filters

### `wc` command:

- `-l`:
- `-w`:
- `-c`:

> ## Logs

### `grep` command:

The grep command in Linux is used to search for patterns within files. It stands for "Global Regular Expression Print".

- Basic usage of grep to search for patterns.

  ```shell
  grep word file.txt
  ```

- `-i` (Ignore Case -> lowercase or uppercase): Ignores case distinctions in patterns and data.
- `-v` (Invert Match): Selects lines that do not match the pattern.
- `-r or -R` (Recursive): Searches recursively through directories.
- `-l` (Lowercase L, Files with Matches): Lists the names of files with matching lines.

  ```shell
  grep -l "pattern" *
  ```

- `-n` (Line Number): Displays line numbers with output lines.
- `-c` (Count): Counts the number of matching lines.
- `-H` (Print Filename): Prints the filename for each match(Displays matching lines with filenames).

### `head` command:

The head command in Linux displays the first few lines of a file or standard input, defaulting to the first 10 lines.

```shell
head fileName.txt
```

- `-n`: Displays the first NUM lines instead of the default 10.

### `tail` command:

The tail command in Linux displays the last few lines of a file or standard input, defaulting to the last 10 lines.

```shell
last fileName.txt
```

- `-n NUM`: Displays the last NUM lines instead of the default 10.

### `watch` command:

The benefit of using the watch command is that it allows you to automatically and continuously execute a command at regular intervals, making it easy to monitor changes in real-time without manually re-running the command.

```shell
watch -n 10 tail /var/log/syslog
```

### `awk` command:

The awk command in Unix-like operating systems is a powerful text-processing utility. It is used to manipulate data and generate reports. It scans a file line by line, splits each line into fields, and processes them according to the instructions provided in a script or directly in the command line.

```shell
awk  '{print $1, $2, $5}'
```

### `sed` command:

The sed command in Unix-like operating systems is a powerful stream editor used for performing basic text transformations on an input stream (a file or input from a pipeline). Its primary use is for search and replace, but it can also perform other text manipulations such as deletion, insertion, and substitution.
