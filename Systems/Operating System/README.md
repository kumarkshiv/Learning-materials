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


# Process states in Linux:
- 

# References:
[1] https://www.oreilly.com/library/view/understanding-the-linux/0596005652/

[2] 

[X] Concurrency in C++: [Modern C++ (cpp) Concurency](https://www.youtube.com/playlist?list=PLvv0ScY6vfd_ocTP2ZLicgqKnvq50OCXM)
