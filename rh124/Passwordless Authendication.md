# Passwordless authedication

#### Ensure that OpenSSH server is installed, If it's not installed.

```
sudo yum install openssh-server   # For older versions
sudo dnf install openssh-server   # For newer versions
```

```
sudo vim /etc/ssh/sshd_config
```

- Port: Change the default SSH port (optional but recommended for security).
- PermitRootLogin: Disable root login for security reasons.
- PasswordAuthentication: Set it to 'no' to enforce key-based authentication only.
- PubkeyAuthentication: Ensure it's set to 'yes' to enable public key authentication.
- AllowUsers: Specify which users are allowed to SSH into the system.

```
sudo systemctl restart sshd
```

#### Generate SSH Key Pair: On the client machine
```
ssh-keygen
```

- Copy Public Key to Server: Once the key pair is generated, you need to copy the public key to the server. You can use the ssh-copy-id command for this:

```
ssh-copy-id username@server_ip
```

- Test SSH Connection: After copying the public key, you should be able to SSH into the server without being prompted for a password:

```
ssh username@server_ip
```
