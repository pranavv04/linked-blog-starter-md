#operatingsystem/process/processscheduling/processtermination
 Processes may also be terminated by the system for a variety of reasons including: 
 - The inability of the system to deliver the necessary system resources.
 - In response to a KILL command or other unhandled process interrupts.
 - A parent may kill its child if the task assigned to them is no longer needed.
 - If the parent exists, the system may or may not allow the child to continue without a parent.
 - When a process ends, all its resources are freed up. The process termination status and execution times are returned to the parent if the parent is waiting for the child to terminate, or eventually returned to init if the process already became an orphan.
 - The processes which are trying to terminate but cannot do so because their parent is not waiting for them are termed as **orphans**.
 - These are eventually inherited by init as orphans and killed off


## Zombie Process:
 -  A process which has finished the execution but still has entry in the process table to report to its parent process is known as a zombie process.
 - A child process always first becomes a zombie before being removed from the process table. 
 - The parent process reads the exit status of the child process which reaps off the child process entry from the process table.


## Orphan Process:
- A process whose parent process no more exists i.e either finished or terminated without waiting for its child process to terminate is called Orphan process