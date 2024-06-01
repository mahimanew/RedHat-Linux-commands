# User and Group Management


## 1. Users

- Normal Users: Regular user accounts.
- System Users: Accounts used by system processes and services.

- Add User: `useradd`
- Delete User: `userdel`
- Modify User: `usermod`
- Change User Password: `passwd`

## 2. Groups

- Primary Group: The default group associated with a user.
- Supplementary Groups: Additional groups a user can belong to.

- Add Group: `groupadd`
- Delete Group: `groupdel`
- Modify Group: `groupmod`


## 3. Creating and Managing Users.

### Create a new user:

```
# Create a new user: sudo useradd username
sudo useradd john
```

```
# Set a password for the new user: sudo passwd username
sudo passwd john
```

```
# Add a user with specific options: 
sudo useradd -d /home/custom_directory -m -s /bin/bash username
```
-d /home/custom_directory: Specifies the user's home directory.
-m: Creates the home directory if it doesn't exist.
-s /bin/bash: Specifies the user's shell.

```
# Modify an existing user: sudo usermod -l new_username old_username
sudo usermod -l john_doe john
```

```
# Delete a user: sudo userdel username
sudo userdel john
```

```
# Delete a user and their home directory: sudo userdel -r username
sudo userdel -r john
```

## 4. Creating and Managing Groups

```
# Create a new group: sudo groupadd groupname
sudo groupadd developers
```

```
# Add a user to a group: sudo usermod -aG groupname username
sudo usermod -aG developers john
```

```
# Remove a user from a group: sudo gpasswd -d username groupname
sudo gpasswd -d john developers
```

```
# Change a user's primary group: sudo usermod -g groupname username
sudo usermod -g developers john
```

```
# Delete a group: sudo groupdel groupname
sudo groupdel developers
```

## 5. Managing Permissions and Ownership

```
# Change file owner: sudo chown user:group filename
sudo chown john:developers /home/john/file.txt
```

```
# Change file permissions: chmod mode filename
chmod 755 /home/john/file.txt
```

## 6. Advanced User and Group Management

```
# Create a user with an expiry date: sudo useradd -e YYYY-MM-DD username
sudo useradd -e 2023-12-31 temporaryuser
```

```
# Set account expiration for an existing user: sudo chage -E YYYY-MM-DD username
sudo chage -E 2023-12-31 john
```

```
# Lock and unlock a user account:
sudo usermod -L username  # Lock
sudo usermod -U username  # Unlock
```

```
# Set password expiration policies:
sudo chage -M max_days username  # Set maximum number of days
sudo chage -m min_days username  # Set minimum number of days
sudo chage -W warning_days username  # Set warning days
sudo chage -I inactive_days username  # Set inactive days
```

### Configuration Files

 - /etc/passwd: Contains user account information.
 - /etc/shadow: Contains secure user account information.
 - /etc/group: Contains group information.
 - /etc/gshadow: Contains secure group information.

 ### Exercise 1: Create a user with a custom home directory and shell

 ```
 # Create a user alice with a custom home directory /home/alice_custom and shell /bin/zsh:

 sudo useradd -d /home/alice_custom -m -s /bin/zsh alice

 # -d /home/alice_custom: Specifies the custom home directory.
 # -m: Creates the home directory if it does not exist.
 # -s /bin/zsh: Specifies the user's shell.
 ```


 ### Exercise 2: Add the user to multiple groups

 ```
 # Add the user alice to the groups developers and designers
 sudo usermod -aG developers,designers alice
```

### Exercise 3: Change the user's password and set an expiration date

```
# hange the password for alice:
sudo passwd alice
# Set an expiration date for the user alice to December 31, 2023:
sudo chage -E 2023-12-31 alice
```

### Exercise 4: Lock the user account and then unlock it
```
# Lock the user alice:
sudo usermod -L alice
# Unlock the user alice:
sudo usermod -U alice
```

### Exercise 5: Delete a user and ensure their home directory is removed

```
sudo userdel -r alice
```

### Exercise 6: Create a group and add multiple users to it

```
# Create a group projectteam:
sudo groupadd projectteam
# Add users john and jane to the projectteam group:
sudo usermod -aG projectteam john
sudo usermod -aG projectteam jane
```

### Exercise 7: Change ownership and permissions of files and directories

```
# Change the ownership of /home/john/file.txt to user john and group projectteam:
sudo chown john:projectteam /home/john/file.txt
# Change the permissions of /home/john/file.txt to rwxr-xr-x (755):
chmod 755 /home/john/file.txt
```





