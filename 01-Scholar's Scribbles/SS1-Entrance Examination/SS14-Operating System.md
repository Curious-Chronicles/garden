---
index: SS14
marks: 5
tags: entrance, operating-system
related: [[]]
status: Completed
created: [[2023-05-06]]
---

## 1. Introduction to Operating System

1. Operating System:
- Definition: An operating system (OS) is a software that acts as an interface between computer hardware and software applications. It manages computer resources, provides a platform for executing programs, and facilitates communication between the user and the computer system. The operating system ensures the efficient utilization of hardware resources, such as the CPU, memory, and devices, and provides services to applications, such as file management, process management, and security.

2. Functions of an Operating System:
   - Process Management: The operating system manages and controls the execution of processes, which are the running instances of programs. It schedules processes, allocates system resources, and provides mechanisms for inter-process communication and synchronization.
   - Memory Management: The operating system handles memory allocation and deallocation, ensuring efficient utilization of available memory. It manages virtual memory, which allows programs to use more memory than physically available by swapping data between memory and disk.
   - File System Management: The operating system provides a file system that organizes and manages files stored on storage devices. It performs file operations like creation, deletion, reading, and writing, and ensures data integrity and security.
   - Device Management: The operating system manages input and output devices, such as keyboards, mice, printers, and disks. It provides device drivers, handles device interrupts, and coordinates the communication between applications and devices.
   - User Interface: The operating system provides a user-friendly interface through which users interact with the computer system. It can be a command-line interface, graphical user interface (GUI), or a combination of both.

3. Types of Operating Systems:
   - Single-User, Single-Tasking: Supports only one user and allows running one program at a time.
   - Single-User, Multi-Tasking: Supports one user but allows running multiple programs concurrently by time-sharing the CPU.
   - Multi-User: Supports multiple users concurrently, allowing each user to run multiple programs simultaneously.
   - Real-Time: Designed for time-sensitive applications, guaranteeing timely response to events within specified time constraints.
   - Distributed: Runs on multiple interconnected computers and provides a unified interface and resource sharing across the network.

Example: Suppose you are using a computer running the Windows operating system. The operating system manages the execution of programs, allocates memory for running processes, handles file operations when you save or open files, controls the input and output devices, and provides a graphical user interface for you to interact with the system.


## 2. Process Management

1. Process:
- Definition: A process is an instance of a program in execution. It represents a running program along with its associated resources, such as memory, files, and devices. Each process has its own execution context, including program counter, stack, and data section.

2. Process States:
   - New: The process is being created and initialized.
   - Ready: The process is waiting to be assigned to a processor for execution.
   - Running: The process is currently being executed by a processor.
   - Blocked: The process is waiting for a particular event or resource to become available.
   - Terminated: The process has finished execution or has been terminated.

3. Process Scheduling:
- Definition: Process scheduling involves the selection of processes from the ready state and allocating them to the CPU for execution. The scheduling algorithm determines the order and priority in which processes are executed.
- Scheduling Algorithms: Different algorithms, such as First-Come, First-Served (FCFS), Shortest Job Next (SJN), Round Robin (RR), and Priority Scheduling, are used to manage process scheduling based on different criteria, such as process arrival time, burst time, and priority.

4. Process Synchronization:
- Definition: Process synchronization ensures that multiple processes can safely access shared resources without conflicts or inconsistencies. It involves the use of synchronization mechanisms, such as locks, semaphores, and monitors, to control access to critical sections of code and prevent race conditions.
- Example: Consider two processes running concurrently and accessing a shared variable. To avoid a race condition where both processes try to modify the variable simultaneously, synchronization mechanisms can be used to ensure that only one process accesses the variable at a time.

5. Inter-Process Communication (IPC):
- Definition: Inter-Process Communication involves the exchange of data and information between processes. It allows processes to cooperate, coordinate, and share data with each other.
- IPC Mechanisms: Different IPC mechanisms, such as shared memory, message passing, pipes, and sockets, are used to facilitate communication between processes.

Example: Suppose you have a system with multiple processes running simultaneously, including a web browser, a media player, and an antivirus program. The operating system manages the execution of these processes, assigns CPU time to each process using scheduling algorithms, ensures synchronization when accessing shared resources, and facilitates inter-process communication when necessary.

Note: The provided information gives a brief overview of process management. Process management is a complex topic with various algorithms and mechanisms. Further exploration and study are recommended to gain a comprehensive understanding.

## 3. Memory Management

1. Memory Hierarchy:
- Definition: Memory hierarchy refers to the organization and arrangement of different types of memory in a computer system. It includes various levels of memory, such as cache, main memory (RAM), and secondary storage (hard disk, solid-state drive).
- Example: In a typical memory hierarchy, the cache memory is the fastest and closest to the CPU, followed by the main memory, and then the secondary storage. Data is transferred between these levels of memory based on the principle of locality to optimize performance.

2. Virtual Memory:
- Definition: Virtual memory is a memory management technique that allows the execution of programs that are larger than the available physical memory. It utilizes a combination of physical memory and secondary storage to create an illusion of a larger address space.
- Example: When a program exceeds the available physical memory, virtual memory allows parts of the program to be temporarily stored on the hard disk while the required portions are loaded into physical memory. This enables efficient utilization of memory resources and supports multitasking.

3. Memory Allocation:
- Definition: Memory allocation is the process of assigning memory blocks to programs and data structures during their execution. It involves managing the allocation and deallocation of memory dynamically.
- Example: In dynamic memory allocation, functions like malloc() and free() in C are used to allocate and release memory blocks respectively. For example, the following code allocates an array of integers dynamically:

```c
int* array = (int*)malloc(5 * sizeof(int));
```

4. Memory Segmentation:
- Definition: Memory segmentation is a memory management technique where memory is divided into variable-sized segments based on logical divisions of a program. Each segment represents a specific portion of a program, such as code, data, stack, or heap.
- Example: In a C program, the code segment stores the program instructions, the data segment stores global and static variables, the stack segment is used for function call and local variables, and the heap segment is used for dynamic memory allocation.

5. Memory Paging:
- Definition: Memory paging is a memory management technique where memory is divided into fixed-sized blocks called pages. These pages are used for both physical and virtual memory addressing.
- Example: In a paging system, the virtual memory of a process is divided into fixed-sized pages, and the physical memory is divided into frames of the same size. The mapping between virtual pages and physical frames is maintained by the operating system using a page table.

## 4. File System Management

1. File System:
- Definition: A file system is a method used by operating systems to organize and store files on a storage device, such as a hard disk or solid-state drive. It provides a hierarchical structure and a set of operations for creating, accessing, modifying, and deleting files.
- Example: In a file system, files are organized into directories (also known as folders). Each file is identified by a unique name and has associated metadata, such as file size, permissions, and creation date.

2. File Allocation Methods:
- Definition: File allocation methods determine how files are allocated and stored on a storage device. Different methods include contiguous allocation, linked allocation, and indexed allocation.
- Example: In contiguous allocation, files are stored in contiguous blocks of disk space. Linked allocation uses linked lists to store files where each block contains a pointer to the next block. Indexed allocation uses an index table to store the addresses of file blocks.

3. File Operations:
- Definition: File operations are the actions that can be performed on files, including creating, opening, reading, writing, and deleting files. These operations are typically provided by the file system interface.
- Example: In C programming, file operations are performed using the functions from the stdio.h library. For example, fopen() is used to open a file, fread() is used to read data from a file, and fwrite() is used to write data to a file.

4. File Attributes and Metadata:
- Definition: File attributes are properties associated with files, such as file name, size, type, permissions, and timestamps (creation, modification, and access). Metadata refers to the collection of all file attributes.
- Example: In a file system, file attributes can be accessed and modified using appropriate system calls or commands. For instance, the "ls -l" command in Unix-like systems displays file attributes, including permissions, owner, group, size, and timestamps.

5. File System Integrity and Recovery:
- Definition: File system integrity refers to the ability of a file system to prevent data corruption and ensure reliable operation. Recovery mechanisms are employed to restore the file system to a consistent state in the event of failures or crashes.
- Example: File system integrity can be ensured through techniques like journaling, which keeps track of changes before they are applied to the file system. In case of a crash, the journal can be used to recover the file system to a consistent state.

## 5. Input/Output Management

1. Input/Output (I/O) Management:
- Definition: I/O management refers to the management and coordination of input and output operations between a computer system and external devices, such as keyboards, mice, monitors, printers, and storage devices.
- Example: When a user types on a keyboard, the input is managed by the operating system, which translates the keystrokes into characters and makes them available to applications. Similarly, when an application sends output to a printer, the operating system handles the data transfer and ensures it reaches the printer correctly.

2. I/O Devices:
- Definition: I/O devices are hardware components used to interact with a computer system. They can be categorized into input devices (e.g., keyboards, mice, scanners) and output devices (e.g., monitors, printers, speakers).
- Example: A user interacts with a computer system through input devices such as a keyboard and a mouse. The system responds by producing output through devices like a monitor or speakers.

3. Device Drivers:
- Definition: Device drivers are software components that facilitate communication between the operating system and hardware devices. They provide an interface for the operating system to control and access device functionality.
- Example: A printer device driver enables the operating system to send print requests to the printer and control various printing options, such as paper size and quality.

4. I/O Operations:
- Definition: I/O operations involve transferring data between the computer system and I/O devices. Common I/O operations include reading input from devices and writing output to devices.
- Example: Reading input from a keyboard involves receiving keystrokes and converting them into characters or commands. Writing output to a monitor involves sending data to be displayed on the screen.

5. I/O Scheduling:
- Definition: I/O scheduling refers to the algorithmic decisions made by the operating system to manage and prioritize I/O operations. It determines the order in which pending I/O requests are serviced to optimize efficiency and fairness.
- Example: A disk scheduling algorithm, such as the Elevator or Shortest Seek Time First (SSTF) algorithm, determines the order in which read and write requests are serviced on a hard disk to minimize seek time and maximize disk throughput.

## 6. Scheduling Algorithms

1. Scheduling Algorithms Overview:
- Scheduling algorithms are used by operating systems to determine the order in which processes or threads are executed on a computer system's CPU. They aim to optimize resource utilization, maximize throughput, minimize response time, and ensure fairness.

2. First-Come, First-Served (FCFS) Scheduling:
- FCFS scheduling is a non-preemptive scheduling algorithm where the processes are executed in the order they arrive. The CPU is allocated to the first process in the queue until it completes its execution.
- Example: If processes P1, P2, and P3 arrive in sequence, they are executed in the order P1, P2, P3 without any preemption.

3. Shortest Job Next (SJN) Scheduling:
- SJN scheduling is a non-preemptive scheduling algorithm that selects the process with the smallest burst time to execute next. It aims to minimize the average waiting time.
- Example: If processes P1, P2, and P3 have burst times of 5, 2, and 8 respectively, the scheduler selects P2 to execute first.

4. Round Robin (RR) Scheduling:
- RR scheduling is a preemptive scheduling algorithm where each process is assigned a fixed time quantum or time slice. The processes are executed in a cyclic manner, with each process getting a chance to execute for a time quantum before being preempted.
- Example: If the time quantum is 4 units and there are processes P1, P2, P3 in the queue, the scheduler allows P1 to execute for 4 units, then suspends it and allows P2 to execute for 4 units, and so on.

5. Priority Scheduling:
- Priority scheduling assigns priorities to processes based on factors such as importance, resource requirements, or user-defined criteria. The process with the highest priority is executed first.
- Example: If processes P1, P2, and P3 have priorities 3, 1, and 2 respectively, the scheduler selects P2 with the highest priority to execute first.

6. Multilevel Queue Scheduling:
- Multilevel queue scheduling organizes processes into multiple queues based on different priority levels or criteria. Each queue may have its own scheduling algorithm, allowing different categories of processes to be treated differently.
- Example: Processes can be categorized into foreground and background queues, with foreground processes having higher priority and being scheduled using an SJN algorithm, while background processes are scheduled using an FCFS algorithm.

## 7. Deadlock

1. Deadlock Definition:
- Definition: Deadlock refers to a state in a computer system where two or more processes are unable to proceed because each is waiting for a resource that is held by another process in the set. It results in a circular dependency of processes, leading to a halt in system progress.
- Example: Consider a system with two processes, P1 and P2, and two resources, R1 and R2. If P1 holds R1 and is waiting for R2, while P2 holds R2 and is waiting for R1, a deadlock occurs.

2. Necessary Conditions for Deadlock:
- Mutual Exclusion: At least one resource must be held in a non-sharable mode, meaning only one process can use it at a time.
- Hold and Wait: Processes are holding resources while waiting for additional resources to be allocated.
- No Preemption: Resources cannot be forcefully taken away from a process; they must be released voluntarily.
- Circular Wait: A circular chain of two or more processes exists, where each process is waiting for a resource held by another process in the chain.

3. Deadlock Handling Techniques:
- Prevention: Techniques to prevent deadlocks by eliminating one or more necessary conditions.
- Avoidance: Techniques to dynamically allocate resources in a way that avoids deadlock by considering resource requests and available resources.
- Detection and Recovery: Techniques to detect the presence of deadlocks and take appropriate actions to recover the system.

4. Deadlock Avoidance Algorithms:
- Banker's Algorithm: A resource allocation algorithm that dynamically analyzes the resource needs of processes before granting resource requests to avoid possible deadlock situations.
- Wait-for Graph: A graphical representation of processes and resources, used to detect potential deadlocks and determine if a system is in a safe or unsafe state.

5. Resource Allocation Graph:
- Definition: A graphical representation of processes and resources, used to analyze the state of resource allocation and identify potential deadlocks.
- Example: In a resource allocation graph, processes are represented by nodes, and resources are represented by edges. A cycle in the graph indicates a potential deadlock.


## 8. Device Management

1. Device Management Overview:
- Device management refers to the management and control of physical and virtual devices in a computer system. It involves handling the interactions between the operating system, device drivers, and various hardware devices.

2. Device Drivers:
- Device drivers are software components that facilitate communication between the operating system and hardware devices. They provide an interface for the operating system to control and access device functions.
- Examples: A device driver for a printer enables the operating system to send print commands and receive status updates from the printer.

3. Device Allocation and Scheduling:
- Device allocation involves assigning devices to processes or threads based on their requests and availability. It ensures fair and efficient utilization of devices.
- Device scheduling determines the order in which processes or threads access devices to avoid conflicts and maximize system performance.

4. Interrupt Handling:
- Interrupts are signals generated by devices to gain attention from the processor. Interrupt handling involves managing and responding to interrupts in a timely manner.
- Examples: When a keyboard generates an interrupt indicating a key press, the operating system interrupts the current execution and handles the key input.

5. I/O Operations:
- Input/Output (I/O) operations involve transferring data between the computer system and external devices. Device management ensures efficient handling of I/O operations.
- Examples: Reading data from a hard disk, writing data to a USB drive, or sending/receiving data over a network.

6. Device Virtualization:
- Device virtualization enables the sharing and virtualization of physical devices among multiple virtual machines or processes. It allows efficient utilization of resources.
- Examples: Virtualizing a network card to be shared by multiple virtual machines, or creating virtual disks using storage virtualization techniques.

## 9. System Calls

1. System Calls Overview:
- System calls are functions or interfaces provided by the operating system that allow user-level processes to interact with the underlying kernel or access privileged resources.
- System calls provide an abstraction layer between user programs and the operating system, enabling processes to perform various operations such as file management, process management, I/O operations, memory management, and network communication.

2. Common System Calls:
- File System Calls: System calls like `open()`, `read()`, `write()`, and `close()` are used to perform file-related operations, such as opening, reading from, writing to, and closing files.
- Process System Calls: System calls like `fork()`, `exec()`, and `exit()` are used to manage processes, including creating new processes, loading new programs into memory, and terminating processes.
- Memory System Calls: System calls like `brk()` and `mmap()` are used to manage memory, such as allocating and freeing memory regions.
- I/O System Calls: System calls like `read()`, `write()`, and `ioctl()` are used for input and output operations, including reading from and writing to devices and performing device-specific control operations.
- Network System Calls: System calls like `socket()`, `connect()`, `send()`, and `recv()` are used for network communication, allowing processes to establish network connections, send and receive data over the network.

3. System Call Invocation:
- To invoke a system call, a process typically uses a library function provided by the operating system, such as `libc` in C. The library function encapsulates the system call and provides an interface that the user program can easily utilize.
- The library function transfers control to the operating system kernel, which then performs the requested operation on behalf of the user program. Once the operation is completed, control is returned to the user program.

4. Examples:
- Example of File System Call (`open()`):
```c
#include <fcntl.h>
#include <sys/types.h>
#include <sys/stat.h>

int main() {
    int fd = open("file.txt", O_RDONLY);
    if (fd == -1) {
        // Handle error
    }
    // File opened successfully, perform operations
    // ...
    close(fd);
    return 0;
}
```

- Example of Process System Call (`fork()`):
```c
#include <sys/types.h>
#include <unistd.h>

int main() {
    pid_t pid = fork();
    if (pid == -1) {
        // Handle error
    } else if (pid == 0) {
        // Child process
        // ...
    } else {
        // Parent process
        // ...
    }
    return 0;
}
```


## 10. Protection and Security

1. Protection and Security Overview:
- Protection and security in the context of computer systems refer to mechanisms and measures put in place to safeguard resources, data, and systems from unauthorized access, malicious activities, and various threats.
- Protection involves controlling access to system resources and ensuring that only authorized entities can perform certain operations or access sensitive information.
- Security focuses on the overall integrity, confidentiality, availability, and reliability of a system, aiming to prevent unauthorized access, data breaches, and other security vulnerabilities.

2. Access Control:
- Access control is a fundamental aspect of protection and security. It involves restricting access to resources based on user identities, privileges, and permissions.
- Access control mechanisms include authentication (verifying user identities), authorization (granting or denying access rights), and auditing (tracking and monitoring user activities).
- Access control can be implemented through mechanisms such as user accounts, access control lists (ACLs), role-based access control (RBAC), and mandatory access control (MAC).

3. Cryptography:
- Cryptography is the practice of securing information by converting it into a form that is unintelligible to unauthorized entities. It involves encryption (converting plaintext into ciphertext) and decryption (converting ciphertext back into plaintext) using cryptographic algorithms.
- Cryptographic techniques protect data confidentiality, integrity, and authenticity, ensuring that data remains secure even if intercepted by adversaries.
- Common cryptographic algorithms include symmetric encryption (e.g., AES), asymmetric encryption (e.g., RSA), and cryptographic hash functions (e.g., SHA-256).

4. Network Security:
- Network security focuses on protecting communication channels, network infrastructure, and data transmitted over networks.
- Techniques such as firewalls, intrusion detection and prevention systems (IDPS), virtual private networks (VPNs), and secure socket layer (SSL) protocols are used to secure network connections and prevent unauthorized access or data interception.
- Network security also involves measures to protect against network-based attacks, such as denial-of-service (DoS) attacks, malware, and network vulnerabilities.

5. Software Security:
- Software security involves ensuring that software systems are resistant to attacks and vulnerabilities that could be exploited by malicious actors.
- Best practices for software security include secure coding practices, input validation, proper error handling, secure configuration, and regular software updates and patches.
- Techniques such as code reviews, penetration testing, and vulnerability scanning are used to identify and mitigate software security risks.

6. Examples:
- Example of Access Control:
  - Using access control lists (ACLs) to define permissions for different user groups on a file server, allowing or denying access to specific files based on user identities and privileges.

- Example of Cryptography:
  - Encrypting sensitive data (e.g., passwords, credit card information) stored in a database using a strong encryption algorithm, ensuring that the data remains secure even if the database is compromised.

- Example of Network Security:
  - Implementing a firewall to monitor and control incoming and outgoing network traffic, filtering out unauthorized access attempts and potential threats.

- Example of Software Security:
  - Conducting a code review to identify and fix security vulnerabilities in a web application, such as input validation flaws that could lead to SQL injection attacks or cross-site scripting (XSS) vulnerabilities.


