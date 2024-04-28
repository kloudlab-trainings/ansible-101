## 1. Introduction to Ansible
- **What is Ansible?**
    - An open-source automation tool.
    - Uses YAML for playbooks.
    - Agentless and works over SSH.
- **Why use Ansible?**
    - Automates repetitive tasks.
    - Easy to learn and use.
    - Wide range of modules available.

## 2. Basic Ansible Commands
- **Check Ansible version:**
    ```shell
    ansible --version
    ```
- **Run a simple command:**
    ```shell
    ansible all -m ping
    ```

## 3. Inventory Management
- **Create an inventory file (`inventory`):**
    ```ini
    [webservers]
    server1 ansible_host=192.168.1.10
    server2 ansible_host=192.168.1.11
    ```
- **Use the inventory file:**
    ```shell
    ansible -i inventory all -m ping
    ```

## 4. Ansible Ad-Hoc Commands
- **Ad-hoc command to install a package:**
    ```shell
    ansible webservers -m apt -a "name=curl state=present" -b
    ```
- **Ad-hoc command to copy a file:**
    ```shell
    ansible webservers -m copy -a "src=/local/path/to/file dest=/remote/path/to/file" -b
    ```

## 5. Ansible Playbooks
- **Structure of a playbook:**
    ```yaml
    ---
    - name: Sample Playbook
      hosts: webservers
      tasks:
        - name: Update apt cache
          apt:
            update_cache: yes

        - name: Install curl
          apt:
            name: curl
            state: present
    ```

- **Running a playbook:**
    ```shell
    ansible-playbook -i inventory sample_playbook.yaml
    ```

## 6. Ansible Roles
- **Create a role structure:**
    ```shell
    ansible-galaxy init my_role
    ```

- **Using a role in a playbook:**
    ```yaml
    ---
    - name: Use a role in playbook
      hosts: webservers
      roles:
        - my_role
    ```

## 7. Ansible Galaxy
- **Download a role from Galaxy:**
    ```shell
    ansible-galaxy install geerlingguy.nginx
    ```

- **Use a role from Galaxy in a playbook:**
    ```yaml
    ---
    - name: Install and configure Nginx
      hosts: webservers
      roles:
        - geerlingguy.nginx
    ```
