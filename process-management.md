`ps` - Gives the list of processes
`echo $$` -  Gives the process id for bash 

$$ is a special Bash variable containing the PID of the current shell.
PID -  your bash process
PPID (Parent Process ID)- Process that started your bash process

STAT 
1. S - Sleep
2. R - Running/Runnable

Example: ps -p ${PID} -o pid,ppid,%cpu,STAT,cmd

`top`- Check the CPU usage percentage


