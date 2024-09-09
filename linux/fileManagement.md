## different between relative and absolute paths:

- A relative path specifies the location of a file or directory relative to the current working directory.

```shell
/docs/document.txt
```

- An absolute path specifies the exact location of a file or directory from the root of the file system.

```shell
/home/user/docs/document.txt
```

## To display files in a clear and organized manner, use this command:

```shell
sudo tree
```

## To display the details of a file, use this command:

This command provides data such as the size of the file, the number of blocks, the user ID of the user accessing the file, and the inode (index) for this file

```shell
stat fileName
```

## links in linux:

1.  Hard Links:

    - A hard link is a direct reference (pointer) to the physical data on the disk.
    - Multiple hard links to a file mean that the file will only be deleted when all links to it are removed.
    - Hard links cannot span different file systems.
    - In a hard link, multiple filenames share the same inode

    ```shell
    ln source_file hard_link_name
    ```

2.  Symbolic (Soft) Links:

    - A symbolic link is a reference to another file or directory in the form of a path.
    - It can link to files or directories on different file systems.
    - If the original file is deleted, the symbolic link becomes a broken link (dangling link).
    - In a soft link, the link has a different inode.

    ```shell
    ln -s source_file soft_link_name
    ```


