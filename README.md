## Currently learning/working on:
1. Agentic AI (DeepLearning.AI): [Link](https://learn.deeplearning.ai/courses/agentic-ai/lesson/pu5xbv/welcome!) : **[100% Done]** : **([Notes](https://github.com/kumarkshiv/Learning-materials/blob/main/AI/README.md))**
2. Operating System concepts:
   ### Virtualization:
      - [The Abstraction: The Process](https://pages.cs.wisc.edu/~remzi/OSTEP/cpu-intro.pdf) **_(Summary)_** 

   		- The **process** is the major OS abstraction of a running program. At any point in time, the process can be described by its state: the contents of memory in its address space, the contents of CPU registers (including the _program counter_ and _stack pointer_, among others), and information about I/O (such as open files which can be read or written).
		- The **process API** consists of calls programs can make related to processes. Typically, this includes _creation_, _destruction_, and other useful calls.
		- Processes exist in one of many different process states, including **running**, **ready** to run, and **blocked**. Different events (e.g., getting scheduled or descheduled, or waiting for an I/O to complete) transition a process from one of these states to the other.
		- A **process list** contains information about all processes in the system. Each entry is found in what is sometimes called a **process control block (PCB)**, which is really just a structure that contains **information about a specific process**.
              
      - [Mechanism: Limited Direct Execution](https://pages.cs.wisc.edu/~remzi/OSTEP/cpu-mechanisms.pdf) **_(Summary)_**

   		- The CPU should support at least two modes of execution: a restricted **user mode** and a privileged (non-restricted) **kernel mode**.
		- Typical user applications run in user mode, and use a **system call** to **trap** into the kernel to request operating system services.
		- The **trap instruction** saves register state carefully, changes the hardware status to kernel mode, and jumps into the OS to a pre-specified destination: the **trap table**.
		- When the OS finishes servicing a system call, it returns to the user program via another special **return-from-trap** instruction, which reduces privilege and returns control to the instruction after the trap that jumped into the OS.
		- The **trap tables** must be set up by the OS at **boot time**, and make sure that they **cannot be readily modified by user programs**. All of this is part of the limited direct execution protocol which runs programs efficiently but without loss of OS control.
		- Once a program is running, the OS must use **hardware mechanisms** to ensure the user program does not run forever, namely the **timer interrupt**. This approach is a **non-cooperative** approach to CPU scheduling.
		- Sometimes the OS, during a timer interrupt or system call, might wish to switch from running the current process to a different one, a low-level technique known as a **context switch**.
      
      - [CPU Scheduling](https://pages.cs.wisc.edu/~remzi/OSTEP/cpu-sched.pdf) **_(Summary)_**

   		- **Scheduling Metrics:**
		   - _**Turnaround Time=**_ (The time at which the job completes) **-** (The time at which the job arrives)
			 ```math
			 T_{turnaround} = T_{completion} - T_{arrival}
			 ```
		   - _**Response Time:**_ (The time the job is scheduled for the first time) **-** (The time from when the job arrives in the system)
			 ```math
			 T_{response} = T_{firstrun} - T_{arrival}
			 ```
		- There are two families of scheduling approaches: **1. STCF** (Shortest Time-to-Completion First) and **2. Round Robin**
		- The first runs the shortest job remaining and thus optimizes **turnaround time** but performs bad in terms of **response time**. 
		- The second alternates between all jobs and thus optimizes **response time**, but at the cost of **turnaround time**. 
		- Both the approaches have an inherent trade-off common in systems. 
		- We have also seen how we might incorporate I/O into the picture, but have still not solved the problem of the fundamental inability of the OS to see into the future (i.e., predicting the nature of the job). 
		- This problem can be solved by a scheduler that uses the recent past about the scheduled jobs and predict the future. This scheduler is known as the multi-level feedback queue (to be studied next).
              
      - [Scheduling: The Multi-Level Feedback Queue](https://pages.cs.wisc.edu/~remzi/OSTEP/cpu-sched-mlfq.pdf) **_(Summary)_**
         -  The Multi-Level Feedback Queue (MLFQ) has multiple levels of queues, and uses feedback to determine the priority of a given job. 
         -	MLFQ pays attention to how jobs behave over time and treat them accordingly. The MLFQ follows below rules to decide how to update priority of the jobs:
	         -	**Rule 1:** If Priority(A) > Priority(B), A runs (B doesn’t).
	         -	**Rule 2:** If Priority(A) = Priority(B), A & B run in round-robin fashion using the time slice (quantum length) of the given queue.
	         -	**Rule 3:** When a job enters the system, it is placed at the highest priority (the topmost queue).
	         -	**Rule 4:** Once a job uses up its time allotment at a given level (regardless of how many times it has given up the CPU), its priority is reduced (i.e., it moves down one queue).
	         -	**Rule 5:** After some time period S, move all the jobs in the system to the topmost queue.
         - MLFQ is interesting for the following reason: instead of demanding a priori knowledge of the nature of a job, it observes the execution of a job and prioritizes it accordingly. In this way, it manages to achieve the best of both worlds: it can deliver excellent overall performance (similar to SJF/STCF) for short-running interactive jobs, and is fair and makes progress for long-running CPU-intensive workloads. 
         - For this reason, many systems, including BSD UNIX derivatives, Solaris, and Windows NT and subsequent Windows operating systems use a form of MLFQ as their base scheduler.

   ### Concurrency:
   ### Persistence:
 
4. Blind 75 (LeetCode.com): [Link](https://leetcode.com/problem-list/oizxjoit/): **[41/75 Done]**

   ![LeetCode Stats](https://leetcard.jacoblin.cool/Shivoid?theme=light&font=Cardo&ext=heatmap) [REF](https://leetcard.jacoblin.cool/)
   
5. Webassembly Tutorial: [Link](https://marcoselvatici.github.io/WASM_tutorial/): **[Started...!!!]**

   - Setup of WASM done in an Ubuntu VM.
   - Tested a simple HelloWorld program in C (Compiled by emcc compiler and generated .js and .html files.)
   - Next: Can we run eBPF/XDP programs using WASM? 
      - eBPF --> User space program (deploy, controls, collects data from kernel programs) + Kernel space program (runs inside the kernel in VM)
      - [uBPF](https://github.com/iovisor/ubpf), [bpftime](https://github.com/eunomia-bpf/bpftime) : eBPF runtime in userspace **(NEED TO EXPLORE)**
   
---

# Resources related to Networks, Systems, Compilers, etc.

## Network (Linux):
- Jiri Benc: The Network Packet's Diary: A Kernel Journey : ([Video](https://www.youtube.com/watch?v=T5TvPRQFNoM)), ([Slides](https://static.sched.com/hosted_files/devconfcz2018/80/packet.pdf?_gl=1*1g2wvgo*_gcl_au*MTE3MzE4Mzk3MC4xNzI2MTE2ODk5*FPAU*MTE3MzE4Mzk3MC4xNzI2MTE2ODk5#page=2.00))
- The control flow (and the associated data buffering) of the Linux networking kernel : ([Link](https://wiki.linuxfoundation.org/networking/kernel_flow#layer_2link_layer_eg_ethernet1))
- The Path of a Packet Through the Linux Kernel : ([Paper](https://www.net.in.tum.de/fileadmin/TUM/NET/NET-2024-04-1/NET-2024-04-1_16.pdf))
- Linux Networking 101 : ([Link](https://www.actualtechmedia.com/wp-content/uploads/2017/12/CUMULUS-NETWORKS-Linux101.pdf))

## eBPF:
- Nice detailed blog on working of eBPF by Bootlin: ([Link](https://bootlin.com/blog/bouncing-on-trampolines-to-run-ebpf-programs/))
- RFC 9669 BPF Instruction Set Architecture (ISA) : ([Link](https://www.rfc-editor.org/info/rfc9669))
- sched_ext: scheduler architecture and interfaces : ([Part1](https://blogs.igalia.com/changwoo/sched-ext-a-bpf-extensible-scheduler-class-part-1/)), ([Part2](https://blogs.igalia.com/changwoo/sched-ext-scheduler-architecture-and-interfaces-part-2/))
- eBPF labs for hands-on: ([Link](https://labs.iximiuz.com/))

## eBPF + AI/LLMs: 
- eBPF × AI/LLMs: The Convergence of System Observability and Artificial Intelligence: [Link](https://eunomia.dev/GPTtrace/)
- Yusheng Zheng (Researcher in **eBPF + AI**): [Website](https://www.yunwei37.com/)
## eBPF + WASM:
- eBPF + Wasm Lightweight Observability on Steroids: [Link](https://kccncna2023.sched.com/event/1R2uf)
  - Deploying eBPF programs through WASM Application (lightweight, 10s of MBs) instead of containers (100s of MBs)

## eBPF + Security/Vulnerabilities:
- DEF CON 33 - Finding and Exploiting Kernel Vulnerabilities in the eBPF Subsystem - Agostino Panico: [Link](https://www.youtube.com/watch?v=TXs5F-7-2aE)

## Defcon for Beginners: [Link](https://www.lastweekasavciso.com/p/a-guide-to-defcon-hacker-conference)

# Resources to prepare for Jobs/Placement:
- **Leetcode:**
  - Blind-75: [Link](https://leetcode.com/problem-list/oizxjoit/)
  - NeetCode-150: [Link](https://leetcode.com/problem-list/plakya4j/)
  - Striver SDE Sheet (117 Questions): [Link](https://leetcode.com/problem-list/eeudwo2i/)
- Algorithms and Datastructures (By Abdul Bari): [Link](https://www.youtube.com/@abdul_bari)
- 4 Minutes Summary - Algorithms and Datastructures (By Michael Sambol): [Link](https://www.youtube.com/playlist?list=PL9xmBV_5YoZO2D89q42-y8voxIJKpB4oR)
- Leetcode Patterns: [Link](https://seanprashad.com/leetcode-patterns/)
  - Questions asked in different companies (Category-wise)
- Visualizing Algorithms and Data structures through animation: [Link](https://visualgo.net/en)
- [Amazon OA Questions (For practice)](http://geeksforgeeks.org/explore?page=1&company=Amazon&difficulty=Medium,Hard&sortBy=difficulty&itm_source=geeksforgeeks&itm_medium=main_header&itm_campaign=practice_header)

# Resources to learn Dynamic Programming:
- Dynamic Programming Playlist (By Aditya Verma): [Link](https://www.youtube.com/playlist?list=PL_z_8CaSLPWekqhdCPmFohncHwz8TY2Go)

# Operating Systems:
- Operating Systems: Three Easy Pieces: [Link](https://pages.cs.wisc.edu/~remzi/OSTEP/)

# AI/LLM:
- [The Smol Training Playbook: The Secrets to Building World-Class LLMs](https://huggingface.co/spaces/HuggingFaceTB/smol-training-playbook#introduction)

# Misc Resources:
- [Inside NVIDIA GPUs: Anatomy of high performance matmul kernels](https://www.aleksagordic.com/blog/matmul)
- [Computer Science from the Bottom Up](https://www.bottomupcs.com/)
- [How Google’s Tensor Processing Unit (TPU) Works?](https://open.substack.com/pub/bytebytego/p/how-googles-tensor-processing-unit?utm_campaign=post-expanded-share&utm_medium=web)
