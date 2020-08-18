## Ansible Set-Up and Files

### Source URL: [https://www.youtube.com/watch?v=BE3oo51J3NE](https://www.youtube.com/watch?v=BE3oo51J3NE) [https://blog.knoldus.com/getting-started-with-ansible-2/](https://blog.knoldus.com/getting-started-with-ansible-2/)

### Introduction to Ansible
- Main purpose: Server configuration.
- Example uses: Keeps all server up to date with packages, you can set up plays on cron/CI server, basically maintenance.
- Maintained by Red Hat.

### Ansible Set-Up

![Ansible Set-up](https://i.ibb.co/7VX5W2K/Screen-Shot-2020-08-18-at-11-17-23.png)
- Needs to be installed to a control machine and dedicated server.
- No need installation in target server, only ssh as connection method. 
- **Control machine** -> Inventory file grouping, naming servers and setting connection.
- **Ad hoc commands** -> Just type one command and apply to specified server/group in inventory file.

### Ansible Files
1. **Inventory:** Gets us connection to each of computer and fleet so we can run commands to all of them or individually.
2. **Playbook:** YAML file, like tasks but include name of playbook, hosts (from inventory), and roles, which is the task route. PLAY Command: `ansible-playbook -i inventory playbook.yml`. Playbooks are divided by function: Upgrading applications, uninstalling applications.
3. **Role:** YAML file includes tasks, package, `with_items` loop through `default/my packages`, `changed_when`. Flexible way of writing, depends on your coding style. File path: `/roles/ansible-role-xxx`.	

![Ansible Set-Up 2](https://i.ibb.co/r7M1rHb/Screen-Shot-2020-08-18-at-11-21-37.png)
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTk5NDQ0OTY2Ml19
-->