# Monitor and manage linux process

#### process is an instance of a running program. Each process in Linux has a unique Process ID (PID) and may have child processes.

- PID (Process ID): Unique identifier for a process.
- PPID (Parent Process ID): PID of the parent process.
- UID (User ID): User identifier of the process owner.
- GID (Group ID): Group identifier of the process owner.
- Priority: Determines the scheduling of the process.

`ps`: Display current processes.
```
ps aux        # Display all processes with detailed information
ps -ef        # Another format to display processes
ps aux | grep <process_name>  # Filter processes by name

pstree        # Display processes in tree format
pstree -p     # Show PIDs

pgrep <process_name>    # Find processes by name
pkill <process_name>    # Kill processes by name

```

`top`: Real-time system monitoring.
```
top           # Start the top utility
```

### Kill command

##### The kill command sends signals to processes. By default, it sends the SIGTERM signal, which politely asks the process to terminate.

##### Common Signals:

- SIGTERM (15): Terminate. This is the default signal sent by kill.
- SIGKILL (9): Kill. Forces the process to terminate immediately.
- SIGHUP (1): Hangup. Often used to instruct daemons to reload configuration files.
- SIGINT (2): Interrupt. Typically sent by pressing Ctrl+C in the terminal.

```
kill <PID>              # Send SIGTERM to a process
kill -9 <PID>           # Send SIGKILL to a process
killall <process_name>  # Kill all processes with the given name
```

#### nice and renice: Change process priority:

```
nice -n 10 <command>   # Start a process with lower priority
renice 15 -p <PID>     # Change the priority of an existing process
```

#### Service management:

- Systemd is a system and service manager for Linux operating systems. 

```
systemctl list-units --type=service  # List all active services

systemctl start <service_name>   # Start a service
systemctl stop <service_name>    # Stop a service
systemctl restart <service_name> # Restart a service
systemctl status <service_name>  # Check the status of a service

systemctl enable <service_name>  # Enable a service to start at boot
systemctl disable <service_name> # Disable a service from starting at boot
```




