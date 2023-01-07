Ansible Role: vim
=========

Ansible role to install vim and vim plugins with Pathogen

Role Variables
--------------

|Variable|Description|Default
---------|-----------|-------
vim_plugins_repositories|List of plugins repositories|[ ]
vim_dotfiles_repo | See [egdoc.dotfiles](https://github.com/egdoc/ansible-role-dotfiles) "dotfiles_repo" variable|""
vim_dotfiles_repo_dest | See [egdoc.dotfiles](https://github.com/egdoc/ansible-role-dotfiles) "dotfiles_repo_dest" variable|~/.dotfiles
vim_dotfiles_files | See [egdoc.dotfiles](https://github.com/egdoc/ansible-role-dotfiles) "dotfiles_files" variable | []
vim_plugins_directory|Directory where to clone plugins|~/.vim/bundle
vim_pathogen_url|Vim-pathogen url|https://tpo.pe/pathogen.vim

Vim dotfiles are deployed (via the egdoc.dotfiles role) only if both the "vim_dotfiles_repo" and "vim_dotfiles_files" variable are populated.

Dependencies
------------

git
egdoc.dotfiles Ansible role (optional)

Example Playbook
----------------

Call role to install a plugin from the default branch:

    - hosts: servers
      roles:
        - role: egdoc.vim
          vim_plugins_repositories:
            - https://github.com/preservim/nerdcommenter

Call role to install a plugin from a specific branch:

    - hosts: servers
      roles:
         - role: egdoc.vim:
           vim_plugins_repositories:
             - { url: 'https://github.com/neoclide/coc.nvim', branch: 'release' }


License
-------

GPLv2

Author Information
------------------

Created by Egidio Docile
