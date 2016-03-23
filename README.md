Role Name
=========

Role that setups up vim for ansible development

Requirements
------------

Outbound internet access as this role will attempt to install EPEL from Fedora.

Example Playbook
----------------

```yml
- hosts: ansibledevbox 
  roles:
    - role: jsmartin.vim-ansible-syntax 
```

License
-------

GPLv2

