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







