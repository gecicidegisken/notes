---
title: what are containers made from
feed: show
date: 16-05-2024
tags:
  - containers
summary: what are containers made from
---
References:

[https://www.youtube.com/watch?v=sK5i-N34im8](https://www.youtube.com/watch?v=sK5i-N34im8) *(jerome petazzoni)*

[https://youtu.be/-7tl9-bYnqE?si=BFifDH6zx05RjZxQ](https://youtu.be/-7tl9-bYnqE?si=BFifDH6zx05RjZxQ) *(ahmet alp balkan)*

---

- Some people tried to grep *lxc* *(short for linux container*) in linux source code. There is no such thing. Or not even “container” *(in the given context)* exists in the source code. That leads us to think “there is no such thing as container in Linux kernel”
    - But there are **cgroups, unshare and chroot** etc.
- Containers are actually using some linux features together. They don’t actullay exist but they are a concept. We can also use these features by ourselves.
- Docker, LXC, systemd etc. are just container runtimes, a program making system calls, making it easy to use all these kernel features together.
    - It is possible to create your own container, using the features, but as always said, don’t roll your own securtiy or in this context, your own container.
- **Repeatible.** They will be the same everywhere, everytime.
- **Secure.** They are on the same OS but there is a security layer and they are isolated from each other.
- **Fast.** Get up and running within seconds and kill within second.

---

### **cgroups**

- Short for control groups
- cgroups are about limiting what you can use, in quantity
- Meter and limit resources (CPU, memory, network) used by processes.
- **memory cgroup:** we can count how much memory is used by a process.
    - The granularity here is not bytes but *memory pages*, which is approx. 4kB in most systems.
- **cpu cgroup:** keep track of user/system CPU time (usage per CPU)
    - It is not wise to actually limit usage of CPU, because we want to use full capacity of it. Also modern computers can slow the CPU down if it is not fully used.

### **namespaces**

- Namespaces limit what you can see
    - You can’t use or affect what you can’t see.
- **PID namespace:** within a PID namespace, processes only see other processes if they are in that PID namespace.
- **network namespace:** processes get their own netwrok resources (interfaces, routing tables, iptables, sockets etc.)
- **user namespace:** this is some kind of security improvement. A process can be “the” root process within a user ns. but in global (host) it is not important & nor privileged.
- **chroot:** select a root directory for a process
- **unshare:** prevent process from seeing&using surroundings (other processes, filesystem etc.)

---

