`ps` - Gives the list of processes
`echo $$` -  Gives the process id for bash 

$$ is a special Bash variable containing the PID of the current shell.
PID -  your bash process
PPID (Parent Process ID)- Process that started your bash process

STAT 
1. S - Sleep (Waiting)
2. R - Running/Runnable
3. T - Stopped

Example: 1. ps -p ${PID} -o pid,ppid,%cpu,STAT,cmd
         2. ps -o pid,ppid,stat,cmd -C sleep

`top`- Check the CPU usage percentage
`pstree -p 3459` - Check the tree of processes
`jobs` - List the jobs
`bg` - Resumes a stopped (paused) job and lets it continue running in the background
`fg` - brings a background or stopped job back into the foreground, so it's attached to your terminal again and you can interact with it directly

SIGSTOP : `kill -STOP PID`
SIGCONT : `kill -CONT PID`
SIGTERM : `kill -TERM PID`

SIGTERM vs SIGKILL

SIGTERM
   ↓
"Please shut down gracefully."
   ↓
Process gets a chance to clean up

-----------------------

SIGKILL
   ↓
"Stop immediately."
   ↓
Kernel terminates the process

Note: 

Process = Linux is executing at the level of Operating System 

Job = something your shell is managing

-------------------------

sleep 300
     ↓
Ctrl + Z -> Stopping
     ↓
bg %1
     ↓
fg %1
     ↓
Ctrl + C -> Termination

---------------------------
S  = sleeping
N  = low-priority/niced process

----------------------------
NI (nice value) influences how much CPU scheduling priority a process gets.
PRI is the priority value used by the scheduler for the kernel scheduling policy 

nice command: `nice -n 10 sleep 500 &` -> Used at the start of a process
renice command: `renice 10 -p PID` -> Used for a process already running

Orphan and Zombie processes

Orphan process: It is a process whose parent process gets killed and Process with PID 1 becomes the parent process.

Zombie process: A zombie is a process that has already finished, but its parent hasn't collected its exit status yet.

`echo $!`: It gives the PID of the most recently started background process.
