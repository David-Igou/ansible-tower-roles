project_create
=========

Create a project in Ansible Tower

Requirements
------------

`ansible.tower` or `awx.awx`

Role Variables
--------------




| Variable                | Required | Default | Choices                   | Comments                                 |
|-------------------------|----------|---------|---------------------------|------------------------------------------|
| tower_project_organization_name       | yes      |         |                           | Organization name to create project under|
| tower_project_name      | yes      | false   |                           | Project name in Tower                    |
| tower_project_description| no      | "Made with Tower Collection"  |     | Tower Project description                |
| tower_project_team      | yes      |         |                           | Team to be given use permission          |
| tower_project_custom_virtualenv | no |       |                           | Custom virtualenv for project            |
| scm_url                 | yes      |         |                           | SCM URL for project                      |
| scm_tag                 | yes      | master  |                           | SCM Branch/Tag for project               |



Dependencies
------------

This role depends on the `ansible.tower` collection

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
---
- name: Playbook for Updating a tower project state and adding an admin
  hosts: localhost
  gather_facts: false
  roles:
    - role: tower/project_create
      environment:
        TOWER_HOST: https://192.168.1.128
        TOWER_USERNAME: admin
        TOWER_VERIFY_SSL: no
      vars: 
        tower_project_organization_name: "Default"
        tower_project_name:
          - "myproject2-dev"
          - "myproject2-qa"
        tower_project_description: "myproject description"
        tower_project_team: "myteam"
        scm_url: "https://github.com/ansible/tower-example.git"
```

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
