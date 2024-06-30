# for example about devices:

/dev/sda1

<!--
sd -> name of device
a  -> device number
1  -> partition number
 -->

<!--
(/) -> root
/dev
/bin
/etc
and so on ....
 -->

# in windows about store c for example:

if the C drive is on disk 0, then any directory in the C drive is also on disk 0 and same partition.

# but in linux

## mounting

To attach a partition or storage device to a directory in your filesystem in Linux, use the mount command if you want to manually specify a directory in a specific partition or storage device.

## Directory Storage:

In Linux, directories and files are stored on disks using a structure known as the filesystem.

- **Filesystems:** A filesystem is a method of organizing and storing files on a disk. Common Linux filesystems include ext4, XFS, and Btrfs. Each filesystem resides on a disk or a partition of a disk.

- **Inodes:** An inode (index node) is a data structure that stores information about a file or directory, such as its size, permissions, timestamps, and disk location. Each file or directory has an inode, but the inode does not store the file's name or its actual data.

- **Directories:** Directories are special types of files that contain a list of filenames and their corresponding inode numbers. When you access a file or directory, the filesystem looks up the inode number in the directory file to find the inode, which then points to the file's data blocks on the disk.

- **Data Blocks:** The actual content of files is stored in data blocks on the disk. The inode contains pointers to these data blocks.

- **Mounting:** Disks or partitions are mounted to directories in the filesystem hierarchy. For example, a disk might be mounted to `/mnt/data`. Once mounted, the directories and files on the disk become accessible as part of the overall directory tree.

- **Disk Partitions:** A disk can be divided into multiple partitions, each potentially containing a different filesystem. Each partition is treated as a separate entity, and files/directories within them are managed by the filesystem on that partition.

## File types in linux

### Displaying File Permissions

If we use the command:

```sh
ls -l
-rw-r--r--
```

first one dash for type file

- (-) refer to file
- (d) refer to directory

## to know ths type of the file use this command

```shell
file fileName
```
