# What is a Process?
- _"A process is usually defined as an instance of a program in execution<sup>[1]<sup>"_
- A Human-being analogy of the process: _"Processes are like human beings. They are generated, they have significant life, they optionally generate one or more child processes and eventually they die."_
- **Note:** _Each process has only one parent_. 
- When a process (child) is created:
  - It is almost identical to its parent. 
  - It receives a (logical) copy of the parent’s address space and executes the same code as the parent, beginning at the next instruction following the **process creation system call.**
- **Parent process** vs **Child process**:
  - Child receives a copy of Parents address space and both share the same pages where the code is present (i.e. **_text_**). Hence, they executes the same code.
  - The child process begins the execution from the next instruction after the process creation system call.
  - The child processes have a separate copies of data (i.e., **_stack_** and **_heap_**) and hence the changes to a memory location by a child processes is **_not vissible_** to the parent process.


- We can see processes in Linux at real time by using the below commands:
  ```
  $ top
  ```
  ```
  $ htop
  ```

# How does the Linux kernel know about each process?
- The Linux OS maintains a **_Process Descriptor_** (a _task_struct_ type structure) to maintain the details about each process to get a clear picture of what each process is doing. For example:
  - Priority of the process.
  - Whether the process is running (on the CPU) or blocked (by an event)?
  - What address space has been assigned to it?
  - Which files the process is allowed to address?
- Let's analyse the **_task_struct_**.
  - Location in Linux:    
    ```$ ls /usr/src/linux-headers-$(uname -r)/include/linux/sched.h ```
  - Link to task_struct in sched.h file : [(Link)](https://elixir.bootlin.com/linux/v6.8/source/include/linux/sched.h#L748)
  - Important fields:
    - ,,

# Process memory layout
- A process memory has four sections:

  1. **Text Section:** The part of the process memory stores the executable code.
  2. **Data Section:** The data section of the process memory stores global variables defined in the code.
  3. **Heap Section:** This section is used to dynamically allocate memory during program run time (i.e., program execution).
  4. **Stack Section:** This memory section stores temporary data (such as: Function parameters, Return addresses and Local variables.)

![alt text](../../Placement%20preparation/images/process_memory_layout.png)

**Ref:** https://www.wiley.com/en-in/shop/general-end-user-computing/operating-system-concepts-10th-edition-p-9781119320913

# Process states in Linux:
- 

# References:
[1] https://www.oreilly.com/library/view/understanding-the-linux/0596005652/

[2] 

[X] Concurrency in C++: [Modern C++ (cpp) Concurency](https://www.youtube.com/playlist?list=PLvv0ScY6vfd_ocTP2ZLicgqKnvq50OCXM)
