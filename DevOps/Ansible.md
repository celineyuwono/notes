## Ansible

### Source URL: [https://www.youtube.com/watch?v=BE3oo51J3NE](https://www.youtube.com/watch?v=BE3oo51J3NE) [https://blog.knoldus.com/getting-started-with-ansible-2/](https://blog.knoldus.com/getting-started-with-ansible-2/)

- Main purpose: Server configuration.
- Maintained by Red Hat.
- Needs to be installed to a control machine and dedicated server.
- No need installation in target server, only ssh as connection method.

screenshot

- Control machine -> inventory file grouping, naming servers and setting connection.
- Ad hoc commands -> Just type one command and apply to specified server/group in inventory file.
- Example use: Keeps all server up to date with packages, you can set up plays on cron/CI server, basically maintenance.

### Components
1. **Inventory** file that gets us connection to each of computer and fleet so we can run commands to all of them or individually.

<![if !supportLists]>2. <![endif]>Playbook: yaml file, like tasks but include name of playbook, hosts (from inventory), and roles, which is the task route. PLAY. Command: ansible-playbook -i inventory playbook.yml. Playbooks divided by function: Upgrading applications, uninstalling applications.

<![if !supportLists]>3. <![endif]>Role: yaml file includes tasks, package, with_items loop through default/my packages, changed_when. Flexible way of writing, depends on your coding style. File path: /roles/ansible-role-bob
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTc5MzI4NjQzNl19
-->