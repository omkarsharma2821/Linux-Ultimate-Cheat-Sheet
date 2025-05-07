# Process Management 

- Process is an instance of a running program 
- e.g python program shell script web server or app server 
- `ps aux | nl #check the no. of running process`
- `ps aux | wc –l #word count` 
- `ps –ef`

**Viewing Processes**

- `ps aux` – View all running processes
- `ps -u username` – View processes for a specific user
- `ps -C processname` – Show a process by name
- `pgrep processname` – Find a process by name and return its PID
- `pidof processname` – Find the PID of a running program

**Managing Processes**

- `kill PID` – Terminate a process by PID
- `pkill processname` – Terminate a process by name
- `kill -9 PID` – Force kill a process
- `pkill -9 processname` – Kill all instances of a process
- `kill -STOP PID` – Stop a running process
- `kill -CONT PID` – Resume a stopped process
- `renice -n 10 -p PID` – Lower priority of a process
- `renice -n -5 -p PID` – Increase priority of a process (requires root)


**Monitoring System Processes**

- `top` - Display running processes and system usage. 
- `htop` - Interactive process viewer. 
free - Show memory usage. 
- `free` –m or free –h – to check the free memory 
- `nproc` – to check no of CPU 
- `ps` - Display current processes. 