> ### Ownership

Ownership in Linux refers to the permissions and control that users and groups have over files and directories, determining who can access, modify, or execute them based on assigned user and group identifiers (UIDs and GIDs)

<!-- what is a different between priamary group and secondary group  -->

#### `chown` command:

- Change the group owner for the file only

  ```shell
  sudo chown :newOwnerGroupForFile fileName
  or
  sudo chgrp newOwnerGroupForFile fileName
  ```

- Change the file owner for the file only

  ```shell
  sudo chown newOwnerFile fileName
  ```

- Change both the file owner and group owner for the file
  ```shell
  sudo chown newOwnerFile:newOwnerGroupForFile fileName
  ```

> ### Permissions

---(user permissions) ---(group permissions) ---(other permissions) file mode

- **Read (r)**: Numeric representation is 4.
- **Write (w)**: Numeric representation is 2.
- **Execute (x)**: Numeric representation is 1. For files, it means the file is executable. For directories, it means you can enter the directory using cd.

#### `chmod` command:

The chmod command is used to change the permissions of a file or directory in Unix-like operating systems, allowing you to set read, write, and execute permissions for the owner, group, and others.

- To change the permissions of a file or directory for User

  ```shell
  sudo chmod u=(-|r)(-|w)(-|x)
  ```

- To change the permissions of a file or directory for Group
  ```shell
  sudo chmod g=(-|r)(-|w)(-|x)
  ```
- To change the permissions of a file or directory for Others
  ```shell
  sudo chmod o=(-|r)(-|w)(-|x)
  ```
- You can use operators like - (subtract) or + (add) for permissions

  ```shell
  sudo chmod (u|g|o)(-|+)(r|w|x) (fileName | directory)
  # for example:
  sudo chmod u+r fileName
  # And you can specify multiple permissions like this:
  sudo chmod u+rw fileName
  # And you can specify multiple types (group, user, others) and permissions using the following format:
  sudo chmod ug-rw
  ```

- Change permissions using numeric representation

  ```shell
  # Sets rwx for owner, rx for group and others
  # Sets read (4) + write (2) + execute (1) for owner, and read (4) + execute (1) for group and others.
  chmod 755 test_file
  # Sets rw for owner, r for group and others
  # Sets read (4) + write (2) for owner, and read (4) for group and others.
  chmod 644 test_file
  ```

#### `getfacl` command:

The getfacl command in Unix-like systems is used to display Access Control Lists (ACLs) for files and directories, showing detailed permissions beyond traditional Unix file permissions.

```shell
getfacl fileName
```
