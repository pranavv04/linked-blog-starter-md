 #operatingsystem/process/processscheduling
   - The act of determining which process is in ready state, and should be moved to the running state is known as **process scheduling**.
   - Prime aim of the process scheduling system is to keep the CPU busy all the time and to deliver minimum response time for all programs.
   - For achieving this, the scheduler must apply appropriate rules for swapping process IN and OUT of CPU.

  Scheduling fell into one of the two general categories:
   - **Non Pre-emptive Scheduling** : When the currently executing process gives up the CPU voluntarily.
   - **Pre-emptive Scheduling**: When the operating system decides to favor another process, pre-empting the currently execution process




## Scheduling queues
  #operatingsystem/process/processscheduling/schedulingqueues 
   - All processes, upon entering into the system, are stored in the **Job Queue**
   - Processes in the Ready state are placed in the **Ready queue**
   - Processes waiting for a device to become available are placed in **Device Queues**
   - A new process is initially put in the **Ready Queue.**
   - It waits in the ready queue until it is selected for execution (or dispatched).


Once the process is assigned to the CPU and is executing, one of the following several events can occur.
 - The process could issue an I/O request, and then be placed in the **I/O queue.**
 - The process could create a new subprocess and wait for its termination
 - The process could be removed forcibly from the CPU, as a result of an interrupt, and be put back in ready queue.


## Operations on Process
#operatingsystem/process/processscheduling/operationonprocess 

  **Process Creation**: 
  - Through appropriate system calls, processes may create other processes.
  - The process which creates other process, is termed as parent of the other process and the sub-process is termed as child
  - Each process is given an integer identifier, termed as process identifier, or PID. The parent PID (PPID) is also stored for each process.
  - A child process may receive some amount of shared resources with its parent depending on system implementation.


**There are two options for the parent process after creating the child:**
- Wait for the child process to terminate before proceeding.
- Run concurrently with the child, continuing the process without waiting.
- It is also possible for the parent to run for a while, and then wait for the child later, which might occur in a sort of a parallel processing operation.




## [[Process Termination]]