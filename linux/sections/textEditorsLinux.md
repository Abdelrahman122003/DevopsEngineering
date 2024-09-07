> # `vim` Editor

## `vi` command:

The vi command in Linux is a text editor used for creating and editing files directly from the command line, offering powerful editing capabilities.

```shell
vi nameOfFile
```

### `Insert Mode`:

Press `i` to insert text.

### `Save and Quit`:

Press `Esc` to exit insert mode, then `:wq` to save and quit.

### `Quit without Saving`:

Press `Esc`, then `:q!` to quit without saving.

### `Navigation`:

Use arrow keys or h, j, k, l for left, down, up, and right movements.

### `Search`:

Press `/` followed by your search term, then Enter.

### `d`:

he d command in vi is used for deleting text. It works in combination with other movements to specify what exactly you want to delete. For example:

### `dw`:

Delete from the current cursor position to the end of the current word.

- d$ or D: Delete from the cursor position to the end of the current line.
- d0 or d^: Delete from the cursor position to the beginning of the current line.

### `w`:

The w command moves the cursor forward by one word. It's used for navigation and combined with other commands like d for operations like deleting to the next word (dw).

### `dd`: The dd command is used to delete entire lines:

- dd: Deletes the entire line where the cursor is currently positioned.
- Prefixing with a number deletes that many lines. For example, 2dd deletes two lines.

> # `nano` Editor

## `nano` command:

The nano command in Linux launches a user-friendly text editor in the terminal, offering basic editing functionalities and keyboard shortcuts for efficient text manipulation and file editing.

```shell
nano nameOfFile
```

### `more` command:

The more command in Linux is used to view the contents of a text file one screen at a time. It allows scrolling forward through the file and provides basic navigation and search functionalities within the terminal environment.

```shell
more fileName
```

### `less` command:

The less command in Linux is used to view the contents of a text file one screen at a time, allowing users to navigate forward and backward within the file using arrow keys or specific commands

```shell
less fileName
```
