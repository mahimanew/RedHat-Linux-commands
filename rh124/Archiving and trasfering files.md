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
