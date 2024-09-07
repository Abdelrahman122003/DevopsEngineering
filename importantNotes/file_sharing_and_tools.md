> ## File Sharing

### `scp` command:

The scp (secure copy) command in Linux securely transfers files and directories between hosts on a network using the SSH protocol

```shell
scp /path/to/local/file username@remote_host:/path/to/remote/destination
```

#### SSH protocol:

    ssh (Secure Shell) often depends on public and private keys for authentication.

    Here's a brief overview of how it works:

    - Key Pair Generation: A user generates a pair of cryptographic keys: a public key and a private key. The private key is kept secure on the user's local machine, while the public key is shared with the remote server.

    - Public Key Distribution: The public key is added to the ~/.ssh/authorized_keys file on the remote server. This file contains a list of all public keys that are authorized to access the server.

    - Authentication Process:

    1. Client Initiates Connection: When the user tries to connect to the remote server using SSH, the client sends a request to the server.
    2. Server Challenge: The server checks its authorized_keys file for the client's public key. If found, the server generates a random string and encrypts it using the client's public key.
    3. Client Response: The client, which has the corresponding private key, decrypts the string and sends it back to the server.
    4. Server Verification: The server verifies that the decrypted string matches the original random string. If it does, the client is authenticated, and the SSH connection is established.

    This method ensures secure authentication without needing to transmit passwords over the network, reducing the risk of interception or brute-force attacks.

### `rsync` command:

The rsync command in Linux is a fast and versatile tool for synchronizing files and directories between two locations over a remote and local network, offering features like incremental transfers, compression, and preservation of file attributes.

```shell
rsync -avz /path/to/local/source username@remote_host:/path/to/remote/destination
# -a (archive mode): preserves permissions, timestamps, symbolic links, etc.
# -v (verbose): shows the progress of the transfer.
# -z (compress): compresses file data during the transfer for faster transmission.
```

### `samba` command:

Samba is a free software suite that provides file and print services to SMB/CIFS clients. It allows for interoperability between Linux/Unix servers and Windows-based clients
