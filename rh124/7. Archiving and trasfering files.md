# Archiving and trasfering files

#### Archiving files involves compressing them into a single file for easier storage or transfer. The most commonly used tool for this purpose in Linux is tar.

### Creating an Archive:
```
tar -cvf archive.tar files/directories
```

- -c: Create a new archive.
- -v: Verbose mode, showing the files being archived.
- -f: Specifies the name of the archive file.

### Viewing Contents of an Archive: 
```
tar -tvf archive.tar
```
- -t: List the contents of an archive.

### Extracting Files from an Archive: 
```
tar -xvf archive.tar
```
- -x: Extract files from an archive.

### Transferring Files:

#### Transferring files between systems in Linux is commonly done using scp (Secure Copy Protocol) or rsync.

### SCP (Secure Copy): SCP allows you to securely copy files between hosts.
```
scp /path/to/local/file username@remotehost:/path/to/remote/location
```

- Replace /path/to/local/file with the path to your local file.
- Replace username with your username on the remote host.
- Replace remotehost with the hostname or IP address of the remote system.
- Replace /path/to/remote/location with the path on the remote system where you want to copy the file.

#### Rsync: Rsync is a powerful tool for synchronizing files and directories between two locations.
```
rsync -avz /path/to/source username@remotehost:/path/to/destination
```

- -a: Archive mode, preserves permissions and other attributes.
- -v: Verbose output.
- -z: Compress file data during transfer to reduce bandwidth.


#### FTP (File Transfer Protocol):

```
# Connecting via FTP:
ftp <hostname or IP>
```


#### SFTP (SSH File Transfer Protocol):

SFTP is a secure version of FTP that encrypts both commands and data, providing a secure way to transfer files over a network. It operates over SSH (Secure Shell)

```
# Connecting via SFTP:
sftp username@hostname_or_IP
```
#### Basic command in both FTP & SFTP:
- ls: List files and directories on the remote server.
- cd: Change directory on the remote server.
- get: Download a file from the remote server.
- put: Upload a file to the remote server.
- quit or exit: Terminate the SFTP session.


#### Differences between FTP & SFTP:
- Security: SFTP encrypts both data and commands, making it more secure than FTP.
- Port: FTP typically uses port 21, while SFTP uses port 22 (SSH default).
- Authentication: FTP often uses username/password for authentication, while SFTP can also use SSH key pairs for authentication, enhancing security.
- Firewall Friendliness: SFTP is more firewall-friendly since it typically uses a single port (port 22) for both data and commands, while FTP requires additional ports for data transfer.
