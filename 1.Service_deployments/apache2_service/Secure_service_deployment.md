# Ansible Roles

An Ansible role is a reusable, self-contained unit of automation that is used to 
organize and manage tasks, variables, files, templates, and handlers in a structured way. 

Roles help to encapsulate and modularize the logic and configuration needed to manage 
a particular system or application component. 

This modular approach promotes reusability, maintainability, and consistency across different 
playbooks and environments.

## Key Components of an Ansible Role

### Tasks
The main list of actions or steps to be executed by the role. 

### Handlers
Tasks that are triggered by changes in other tasks, typically used for actions like restarting services.

### Templates
Contains file template which supports modifications from the role. We use the Jinja2 templating language for creating templates.Jinja2 templates that can be rendered and transferred to managed hosts.

### Vars
Contains variables for the role. Variables in vars have higher priority than variables in defaults directory

### Defaults
Contains default variables for the role. Variables in default have the lowest priority so they are easy to override

### Meta
Metadata about the role, contains metadata of role like an author, support platforms, dependencies.

### tests/
Contains test playbooks and inventory to test the role locally before using it in production.
-  inventory → defines test hosts (like localhost).
-  test.yml → a minimal playbook that applies the role for testing.

### Library
Custom modules or plugins used within the role.

### Module_defaults
Default module parameters for the role.

### Lookup_plugins
Custom lookup plugins for the role.

## Directory Structure of an Ansible Role

An Ansible role follows a specific directory structure:

```
apache2/
├── README.md
├── defaults
│   └── main.yml
├── handlers
│   └── main.yml
├── index.html
├── meta
│   └── main.yml
├── tasks
│   └── main.yml
├── tests
│   ├── inventory
│   └── test.yml
└── vars
    └── main.yml
```
| Folder/File       | Purpose                                              |
| ----------------- | ---------------------------------------------------- |
| defaults/main.yml | Default variables (lowest priority)                  |
| vars/main.yml     | Variables with higher priority, usually fixed values |
| tasks/main.yml    | Main tasks to perform (install, configure, deploy)   |
| handlers/main.yml | Handlers triggered on change (restart service)       |
| meta/main.yml     | Role metadata, dependencies                          |
| tests/            | Contains inventory and playbook for testing the role |
| index.html        | Demo web page content                                |
| README.md         | Documentation about the role                         |

## Why Use Ansible Roles?

### Modularity
Roles allow you to break down complex playbooks into smaller, reusable components. 
Each role handles a specific part of the configuration or setup.

### Reusability
Once created, roles can be reused across different playbooks and projects. This saves time 
and effort in writing redundant code.

### Maintainability
By organizing related tasks into roles, it becomes easier to manage and maintain the code. 
Changes can be made in one place and applied consistently wherever the role is used.

### Readability
Roles make playbooks cleaner and easier to read by abstracting away the details into logically
named roles.

### Collaboration
Roles facilitate collaboration among team members by allowing them to work on different parts
of the infrastructure independently.

### Consistency
Using roles ensures that the same setup and configuration procedures are applied uniformly across
multiple environments, reducing the risk of configuration drift.
