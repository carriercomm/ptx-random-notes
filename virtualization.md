Virtualization
===

###concepts:

- **virtualized conponents** 
may include hardware platforms, operating systems, storage devices, network devices, or other resources

- **the usual goal of virtualization** 
centralize administrative tasks while improving scalability and overall hardware resource utilization

- **things virtualization can accomplish**
several operating systems can be run in parallel on a single CPU

###taxonamy

- **full virtualizaton** 
e.g. VMware Workstation, VMware Server, KVM, Hyper-V, VirtualBox, Oracle VM, Parallel Workstation
- **partial virtualization** 
- **paravitualization**
- **operating system level virtualizaion**
e.g. OpenVZ, FreeBSD jails, Solaris Containers, Linux-VServer, Parallel Virtuozzo Containers




hardware assisted virtualization 
   -- the hardware provides architectural support that facilitates building a virtual machine monitor and allows guest OSes to be run isolation

Hypervisor
---
hypervosor i.e. VMM (virtual machine manager) is software/firmware/hardware that creates and runs virtual machines 

`host machine` -- computer the hypervisor runs on 
`guest machine` -- the virtual machines

###taxonamy

- **Type 1 Native** (bare metal) - the hypervisor runs directly on the host's hardware, control the hardware and manage guest operating systems, e.g. Hyper-V
- **Type 2 Hosted** - the hypervisor runs on a conventional operating system e.g. KVM, VM workstation, virtualbox



OS-level virtualization
---

###OpenVZ                

- OpenVZ for open virtuozzo
- it is a OS-level virtualization technology
- it allows a physical server to run multiple operating system instances i.e. containers
- it is not true virtualization but really containerization (like FreeBSD Jails)
- uses a single patched linux kernel and therefore can only run linux

Full Virtualization
---

###Xen

- it is free software under GPL available for IA-32, x86-64, and ARM
- it is a hypervisor allow multiple computer operating system execute on the same hardware concurrently

