## Currently learning/working on:
1. Agentic AI (DeepLearning.AI): [Link](https://learn.deeplearning.ai/courses/agentic-ai/lesson/pu5xbv/welcome!) : **[70% Done]**
   . . .
   
   A. Module-4:
      - . . .
      - **Hands-on: Adding component-level evaluation to your Agenti Workflow:**
         i. When your Agentic workflow is complex, when one component is performing poorly --> Doing an end-to-end evaluation is time-consuming.
         ii. It is difficult to see the end-to-end improvement by just improving one component. (Due to randomness introduced by other components).
         iii. Do component-level evaluations.
           - Identify the component performing poorly.
           - Design an evaluation for that component --> Add this evaluation to your Agentic workflow.
           - Example: **Web Search** of a research workflow.
             - See if the component is returning the URLs from your list of preferred domains.
             - Compute the ratio of **preferred** vs **total results**.
             - Return **PASS / FAIL** for a prompt.
            
      - **Practical tips for Building Agentic AI**:
         i. Improving **non-LLM** components performance:
           - Tune hyperparameters of the components (e.g., # results, date range in websearch component, etc.)
           - Replace the component (e.g., try a different web search engine, etc.)
         ii. Improving **LLM** components performance:
           - Improve your prompts (e.g., add more explicit instructions or examples to prompt, use **few-shot** prompting, etc.)
           - Try different LLMs and use evaluations to pick the best model. **(Need skill to identify a good model)**
           - If a task is too complex for the model --> **Decompose** the task into multiple steps (e.g., Generation, reflection, etc.)
                   
      - **Q) How can you identify a good model for a particular task?**
         - Play with different models. (Have a set of evaluations, read other people's prompts for ideas of how to best use models, etc.)
         - Use different models in your Agenti workflow (Observe which model works better for which type of tasks, use easy-to-use libraries like [Aisuite](https://github.com/andrewyng/aisuite))
   
3. Blind 75 (LeetCode.com): [Link](https://leetcode.com/problem-list/oizxjoit/): **[41/75 Done]**
4. Webassembly Tutorial: [Link](https://marcoselvatici.github.io/WASM_tutorial/): **[Started...!!!]**
   
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
