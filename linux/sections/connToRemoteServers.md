> # Connecting to remote servers

**First thing install it**
    
## SSH(Secure Shell) Protocol

The SSH (Secure Shell) protocol is a network protocol used for secure remote administration and file transfers over an insecure network. Key features include:

- Encryption: SSH encrypts data to ensure that the communication between the client and server is secure from eavesdropping.
- Authentication: It uses methods like password-based or key-based authentication to verify the identity of users.
- Data Integrity: SSH ensures that data sent over the network is not tampered with or altered during transmission.
- Port Forwarding: It supports forwarding network ports and tunneling to securely access other services through the SSH connection.


SSH is commonly used for managing servers, transferring files securely, and executing commands on remote machines.


### Connent Using SSH(using username and password)


1. Use the following command to connect to the server:    

    ```s
    ssh <user>@<ip-address>
    ```
    Replace <user> with your username and <ip-address> with the IP address of the server you want to connect to.
    
    Enter server password when prompted.

2. Alternative method to log in:
   ```s
   ssh <ip-address-server>
   ```

   This method assumes your username on the server is the same as your local username. Enter the server password when prompted.
3. Simplify Login with SSH Configuration

    Instead of typing the full SSH command every time you log in to a remote machine, you can configure SSH to simplify the process:

    1. Create or edit the SSH configuration file:

        Go to the .ssh directory in your home folder:
        ```s
        cd ~/.ssh
        ```
        If the config file does not exist, create it:
        ```s
        touch config
        ```

        Open the config file with a text editor:
        ```s
        nano config
        ```
    2. Add the following configuration:
        ```s
        Host MyLocalHost
          Hostname 127.0.0.1
          Port 22
          User boda
        ```
        Replace MyLocalHost with a name of your choice, 127.0.0.1 with the server's IP address, and boda with your username on the server.
    3. Save and close the file.
    4. Connect to the server using the simplified command:
        ```s
        ssh MyLocalHost
        ```
    This command will use the configuration you specified in the config file.
4. execute command only
   
   ```s
   ssh <user>@<ip-address> <command>
   ```
   Replace `user` with your username, `ip-address` with the server's IP address, and `command` with the command you want to execute. Enter the server password when prompted.

### Authentication with Remote Server Using Public and Private Keys


- **`Explanation`**
  
  We have another method for authenticating with a remote server that uses a public and private key pair, instead of relying on a username and password


    Here's a brief overview of how it works:

    - Key Pair Generation: A user generates a pair of cryptographic keys: a public key and a private key. The private key is kept secure on the user's local machine, while the public key is shared with the remote server.

    - Public Key Distribution: The public key is added to the ~/.ssh/authorized_keys file on the remote server. This file contains a list of all public keys that are authorized to access the server.

    - Authentication Process:

    1. Client Initiates Connection: When the user tries to connect to the remote server using SSH, the client sends a request to the server.
    2. Server Challenge: The server checks its authorized_keys file for the client's public key. If found, the server generates a random string and encrypts it using the client's public key.
    3. Client Response: The client, which has the corresponding private key, decrypts the string and sends it back to the server.
    4. Server Verification: The server verifies that the decrypted string matches the original random string. If it does, the client is authenticated, and the SSH connection is established.

    This method ensures secure authentication without needing to transmit passwords over the network, reducing the risk of interception or brute-force attacks.

- **`Generate the private and public keys`**
  
    Command to generate the private and public keys

    ```s
    ssh-keygen
    ```   
- **`Steps to Add the Public Key to a Remote Machine`**
  
   - Log in to the remote machine.
   - Navigate to the `~/.ssh` directory.
   - Append your public key to the `authorized_keys` file
  
   Make sure the authorized_keys file has the correct permissions:

   ```s
   chmod 600 ~/.ssh/authorized_keyss
   ```

- **`Another method to copy the public key`**
  
  This command takes the public key from a file on your local machine and adds it to the authorized_keys file on the remote machine.


  ```s
  ssh-copy-id -i <public-key-file> <your-name>@<ip-server>

> ## File Sharing

### `scp` command:

The scp (secure copy) command in Linux securely transfers files and directories between hosts on a network using the SSH protocol

```shell
scp /path/to/local/file username@remote_host:/path/to/remote/destination
```

### `rsync` command:

The rsync command in Linux is a fast and versatile tool for synchronizing files and directories between two locations over a remote and local network, offering features like incremental transfers, compression, and preservation of file attributes.

```shell
rsync -avz /path/to/local/source username@remote_host:/path/to/remote/destination
```
```shell
# -a (archive mode): preserves permissions, timestamps, symbolic links, etc.
# -v (verbose): shows the progress of the transfer.
# -z (compress): compresses file data during the transfer for faster transmission.
```

### `samba` command:

Samba is a free software suite that provides file and print services to SMB/CIFS clients. It allows for interoperability between Linux/Unix servers and Windows-based clients


### `wget` command:

wget is a command-line utility for downloading files from the internet. It is widely used for non-interactive downloads, meaning it can work in the background without needing user interaction.


### `curl` command: 

The `curl` command is a versatile tool used for transferring data to and from servers. It supports various protocols, including HTTP, HTTPS, FTP, FTPS, SCP, SFTP, and more.

### `w3m` command:

w3m is a text-based web browser for Unix-like systems. It allows you to browse the web from the terminal, making it useful for accessing web content without a graphical user interface.