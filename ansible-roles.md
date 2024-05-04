Ansible Role
How to use an ansible role
Ansible-Galaxy and creating your own role
Role Structure

role-name/
├── defaults/
│   └── main.yml
├── files/
│   └── (static files)
├── handlers/
│   └── main.yml
├── meta/
│   └── main.yml
├── tasks/
│   └── main.yml
├── templates/
│   └── (Jinja2 templates)
├── tests/
│   ├── inventory
│   ├── test.yml
│   └── (test files)
├── vars/
│   └── main.yml
├── README.md
└── (other role-specific files)


Ansible Templates and Jinja2
How Templates Work:
 Template File
 Variables
 Template Rendering
 
How to Use Templates:
 Create a Template File:
 Include the Template in a Playbook:
 Include the Template in a role
 


