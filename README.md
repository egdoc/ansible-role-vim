Ansible Role: vim
=========

Ansible role to install and configure vim on Linux

Requirements
--------------
None

Role Variables
--------------

Available variables are the following:

```yaml
vim_global_editor: false
```

Whether Vim should be set as the default text editor globally.

```yaml
vim_install_gvim: false
```

Whether the GUI version of Vim should also be installed.

Dependencies
------------
None

Example Playbook
----------------

Install Vim and set it as the global editor:

```yaml
- hosts: servers
  roles:
    - role: egdoc.vim
      become: true
      vim_global_editor: true
```

License
-------

GPLv2

Author Information
------------------

Created by Egidio Docile
