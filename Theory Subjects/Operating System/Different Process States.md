#operatingsystem/process/processstates
Process in the operating system can be in any following states:
- **NEW** : The process is being created.
- **READY** : The process is waiting to be assigned to a processor
- **RUNNING** : Instructions are being executed
- **WAITING** : The process is waiting for some event to occur (such as an I/O completion or reception of a signal)
- **TERMINATED** : The process has finished execution.

![[k093y86c.png]]

## Process Control Block
#operatingsystem/process/processcontrolblock 
  - There is a process control block for each process, enclosing all the information about the process. It is a data structure, which contains the following
  - **Process State** : It can be running, waiting, etc.
  - **Process ID** and the **parent process ID**.
  - CPU registers and Program Counter. **Program Counter** holds the address of the next instruction to be executed for that process.
  - **CPU Scheduling** information:  Such as priority information and pointers to scheduling queues.
  - **Memory Management Information**: Example => page tables or segment tables.
  - **Accounting Information** : The User and kernel CPU time consumed, account numbers, limits, etc.
  - **I/O Status information** : Devices allocated, open file tables, etc.


## [[Process Scheduling]]


