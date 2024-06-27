# types of users in linux

super user -> root
normal user -> me
system user -> software(remove files, add files, install packages .....)

-every user has UID(user id, home directory, ...)
root -> 0
system user -> 1 => 999
normal user -> 1000 => ....

## To list all users with their user IDs:

```shell
cat /etc/passwd
```

## Identify who has administrative privileges, and you can add users to grant them privileges.

```shell
cat /etc/sudoers
```

`su`: The su command in Linux is used to switch the current user account to another user account, typically to gain superuser (root) privileges

`adduser`: The adduser command in Linux is used to create a new user account with default settings and configurations.

- `m`: using the -m option ensures the creation of a home directory for the user
- `c`: The -c option in the adduser command in Linux allows you to specify a comment or additional information about the user being created.
- `p`: This option allows setting a password directly during the user creation process, ensuring the account is secured upon creation.

`userdel`: The userdel command in Linux is used to delete a user account and its associated files from the system

- `r`: using the -r option also removes the user's home directory and mail spool.

`passwd`: The passwd command in Linux is used to manage user account passwords, allowing users to change their own passwords or administrators to set passwords for other users.

`usermod`: The usermod command in Linux is used to modify user account attributes and settings, such as changing the username, user ID, group ID, home directory, shell, and more.

- `usermod -aG`: The usermod -aG command in Linux is used to add a user to additional supplementary groups without removing them from their current groups

  ```shell
  sudo usermod -aG group1 zoombie
  ```

- `usermod -rG`: The usermod -rG command in Linux is used to remove a user from specified supplementary groups, effectively modifying the user's group membership settings.

  ```shell
  sudo usermod -rG group1 zoombie
  ```

## groups

Groups in Linux serve the purpose of organizing users with similar permissions and access rights, allowing efficient management of file permissions, resource access, and security policies across multiple users

`groups` command : The groups command in Linux displays the groups to which a user belongs, showing both primary and supplementary groups

```shell
groups
```

`groupadd` command: The groupadd command in Linux is used to create a new group, allowing administrators to organize and manage users with shared permissions and access rights

```shell
groupadd groupName
```

`groupdel` command: The groupdel command in Linux is used to delete a specified group from the system, removing its association with users and potentially deleting its group directory and files if empty.

```shell
groupdel groupName
```
