# ansible-101
Ansible 101 training


Reference: https://github.com/omerbsezer/Fast-Ansible/

Ansible is an agentless automation that automates deployment, configuration management (maintain infrastructure consistency) and orchestration (execution of multiple applications in order). Ansible gains it’s popularity due to it’s simplicity for being agentless, efficient, requires no additional software installed on target machine, use the simple YAML and complete with reporting.

Ansible architecture is very simple. It requires Ansible Server basically a node (laptop, PC or server) where Ansible is installed with the module of configuration files called playbook and inventory of target servers called hosts. Playbook consists of Roles, and Roles consists of Tasks. Task is an individual command in Ansible. By using inventory we group the nodes by using labels.

Ansible Server and the node talks by using passwordless SSH.

Flow of working with Ansible:

    Create playbook and inventory in local machine
    Create SSH to the target nodes
    Ansible Server gathers the facts of the target nodes to get the indication of the target nodes
    Playbook are sent to nodes
    Playbook are executed in the nodes

![alt text](1_8H4XYCNV-xamG0joz22apQ.png)

Important Terms

**Ansible server**: The machine where Ansible is installed and from which all tasks and playbooks will be ran

**Module**: Basically, a module is a command or set of similar commands meant to be executed on the client-side

**Task**: A task is a section that consists of a single procedure to be completed

**Role**: A way of organizing tasks and related files to be later called in a playbook

**Fact**: Information fetched from the client system from the global variables with the gather-facts operation

**Inventory**: File containing data about the ansible client servers. Defined in later examples as hosts file

**Play**: Execution of a playbook

**Handler**: Task which is called only if a notifier is present

**Notifier**: Section attributed to a task which calls a handler if the output is changed

Tag: Name set to a task which can be used later on to issue just that specific task or group of tasks.


