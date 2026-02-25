Linux Architecture Notes
1. Core Components of Linux
Kernel (Core of the OS)

Acts as the bridge between hardware and software

Manages CPU, memory, devices, and file systems

Handles process scheduling, memory management, and I/O operations

Runs in privileged mode

User Space

Where normal programs execute (shell, apps, utilities)

Cannot directly access hardware

Interacts with kernel via system calls

Init System (systemd)

First process started by the kernel (PID 1)

Responsible for bootstrapping the system

Starts and manages background services (daemons)

2. Process Fundamentals
What is a Process?

A running instance of a program

Identified by PID (Process ID)

Has its own memory space and resources

Process Creation

Created using fork() → duplicates parent

Often followed by exec() → loads new program

Parent / Child relationship maintained

3. Process States (Important for Troubleshooting)

Running (R) → Currently executing or ready to run

Sleeping (S) → Waiting for event (very common)

Stopped (T) → Suspended manually or by signal

Zombie (Z) → Finished execution but not cleaned by parent

Uninterruptible Sleep (D) → Waiting on I/O (disk/network)

Zombie processes indicate poor process cleanup.

4. How Linux Manages Processes

Kernel scheduler allocates CPU time

Priority & niceness influence scheduling

Context switching enables multitasking

Signals control process behavior (kill, SIGTERM, etc.)

5. What systemd Does

systemd is the modern Linux init system.

Key responsibilities:

Starts services during boot

Manages background daemons

Handles service restarts & failures

Tracks dependencies between services

Provides logging via journald

Why it matters:

Centralized service control

Faster boot times

Consistent management across distros

6. Daily Commands (High Practical Value)

ps aux → View running processes

top / htop → Monitor CPU & memory usage

systemctl status <service> → Check service health

systemctl restart <service> → Restart services

journalctl -u <service> → View service logs

7. Why This Knowledge Matters

Understanding Linux internals helps to:

Diagnose crashed services

Identify CPU / memory bottlenecks

Debug stuck or zombie processes

Analyze logs effectively

Respond faster during incidents
