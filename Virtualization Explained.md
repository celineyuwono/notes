<![endif]-->

Virtualization Explained

[https://www.youtube.com/watch?v=FZR0rG3HKIk](https://www.youtube.com/watch?v=FZR0rG3HKIk)

- Create software-based version of applications, etc.
- Make virtualization feasible: hypervisor.
- Hypervisor: Physical software that runs above server, pull resources from physical server and allocate to virtual environment.
	- Type 1 (Bare Metal): Installed directly on top of server, most frequent, most secure, lower latency.
	- Type 2 (Hosted): Have layer of Host OS between host and hypervisor, higher latency.
- After hypervisor installed, you can install VM: Software-based computer, can run multiple on top of hypervisor. Hypervisor manages resources allocated to these VM from physical server. You can run different OS in different VMs. Extremely portable, can move VM from one hypervisor to another easily.
- Benefits of Virtualization: Cost saving (can run multiple VM in 1 physical server, don’t have to have many servers), agility and speed (run new environment easily), lower down time (if server goes down, move VM to another server).
<!--stackedit_data:
eyJoaXN0b3J5IjpbOTEwNjA2ODgyXX0=
-->