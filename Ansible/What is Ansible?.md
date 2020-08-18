## What is Ansible?

### Source URL: [https://www.youtube.com/watch?v=1id6ERvfozo](https://www.youtube.com/watch?v=1id6ERvfozo)

- Ansible is an automation tool that:
	- Execute tasks from own machine, no need ssh.
	- Configuration/installation/deployment steps in a single YAML file instead of manual shell scripts.
	- Re-use same file multiple times for different environments.
- Ansible is agentless, no Ansible file on target servers. So no need to deploy Ansible. Only in your laptop!
- Ansible work with Modules. Modules are small program that actually does the work. Modules get sent from the control machine (your laptop) to the target server and do their job in the target server like configuration/installation/etc When they are done, they get removed. 1 Modules are very granular, 1 module = 1 specific task. Ansible can execute tasks because it has all these modules. See list of modules in Ansible documentation.

![Ansible Screenshot](https://i.ibb.co/N2jfz42/Screen-Shot-2020-08-18-at-9-44-42.png)

- Ansible Playbooks are multiple modules group and sequenced together in a file. `Modules -> Tasks = 1 configuration`.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTkxMDE2MDIzN119
-->