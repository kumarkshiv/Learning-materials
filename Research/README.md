**Community Meetup:** [PATCH v2] Linux Kernel & eBPF Meetup 

**Meetup Link:** https://kernel-ebpf-meetup.github.io/?utm_source=luma

- **Date:** 1/Aug/2026

- Paper discussed: [The Fabric Is the Cluster Driver: Cross-Layer eBPF Policies for GPU-CXL Fabrics](https://arxiv.org/abs/2607.26335)
- Key Idea:
  
  - Normally, host CPU sees everything and take decisions using the metrics collected by in-kernel programs like eBPF, etc.
  - The idea is moving this decision overhead to the fabric (GPU + DPU + CXL devices) and the decision is taken autonamously by the fabric.
  - The current AI architecture not only contains CPU and GPU. There are new devices that are being used like DPU, NPU, CXL, etc for seamless operation (training and inference) of LLM models in the distributed manner.
  - eBPF programs at fabric, i.e. GPUs, DPUs, Switches, NICs and CXL generate the useful metric info. and All other device in the infra will use this collected information for better and efficient decisions.
  - eBPF attached to DPUs will be more effective than in CPU  -->  We can generate computational DAG at CPU level  -->  Generating such graph is difficult with eBPF currently (due to lack of expressiveness)
  - Compute arbirary metric you need (from the devices in your fabric) and use the info. for better decisions.
  - 