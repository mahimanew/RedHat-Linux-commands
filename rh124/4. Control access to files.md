# control access to files

### In Linux, each file and directory has a set of permissions that determine who can read, write, or execute them.

- Owner (u): The user who owns the file.
- Group (g): The group that owns the file.
- Others (o): All other users.

### Each of these categories can have three types of permissions:

- Read (r): Permission to read the file.
- Write (w): Permission to modify the file.
- Execute (x): Permission to execute the file (if it's a script or binary).

- Read (r) = 4
- Write (w) = 2
- Execute (x) = 1

#### Example:

 - 7: rwx (4 + 2 + 1 = 7)

        Read (4)
        Write (2)
        Execute (1)
 - 5: r-x (4 + 0 + 1 = 5)

        Read (4)
        No write (0)
        Execute (1)

```
#view file permissions: 
ls -l filename
```

### To change file permissions, use the chmod command:

- `chmod` is used to change the file permissions of a file or directory.

```# Change permissions using symbolic mode
chmod u+rwx, g+rx, o+r filename

# Change permissions using numeric mode
chmod 755 filename
```

### To Changing Ownership, use the chown command:

 - `chown` is used to change the owner and/or group of a file or directory.

```
 # Change the owner to user1
chown user1 filename
```

```
# Change the group to group1
chown :group1 filename
```

```
# Change the owner to user1 and group to group1
chown user1:group1 filename
```

### To Change Group, use the chgrp command:

- `chgrp` is used to change the group ownership of a file or directory. 

```
# Change the group to group1
chgrp group1 filename
```

### Differences Between chmod, chown, and chgrp
#### Purpose:

    - chmod: Changes the permissions of a file or directory.
    - chown: Changes the owner and/or group of a file or directory.
    - chgrp: Changes only the group ownership of a file or directory.

#### Usage:

    - chmod: Used to control read, write, and execute permissions.
    - chown: Used to assign a new owner and optionally a new group.
    - chgrp: Used to assign a new group without changing the owner.

#### Example Scenario:

    - chmod: You want to give the group write permissions to a file.
    - chown: You want to transfer ownership of a file to another user.
    - chgrp: You want to change the group ownership of a file to a different group.

### Example1 : Practice Scenario

#### Changing Permissions with chmod:
```
# Create a file
touch example.txt

# Check current permissions
ls -l example.txt
# Output: -rw-r--r-- 1 user user 0 Jun  1 10:00 example.txt

# Add execute permission for the owner
chmod u+x example.txt

# Check updated permissions
ls -l example.txt
# Output: -rwxr--r-- 1 user user 0 Jun  1 10:00 example.txt
```

### Example2 : Practice Scenario

#### Changing Owner with chown:
```
# Check current ownership
ls -l example.txt
# Output: -rw-r--r-- 1 user user 0 Jun  1 10:00 example.txt

# Change owner to user2
sudo chown user2 example.txt

# Check updated ownership
ls -l example.txt
# Output: -rw-r--r-- 1 user2 user 0 Jun  1 10:00 example.txt
```

### Example3 : Practice Scenario

#### Changing Group with chgrp:
```

# Check current group ownership
ls -l example.txt
# Output: -rw-r--r-- 1 user user 0 Jun  1 10:00 example.txt

# Change group to group2
sudo chgrp group2 example.txt

# Check updated group ownership
ls -l example.txt
# Output: -rw-r--r-- 1 user group2 0 Jun  1 10:00 example.txt
```





