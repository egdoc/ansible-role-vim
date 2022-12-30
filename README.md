Ansible Role: vim
=========

Ansible role to install vim and vim plugins with Pathogen

Role Variables
--------------

|Variable|Description|Default
---------|-----------|-------
vim_plugins_repositories|List of plugins repositories|[ ]
vim_plugins_directory|Directory where to clone plugins|~/.vim/bundle
vim_pathogen_url|Vim-pathogen url|https://tpo.pe/pathogen.vim

Dependencies
------------

git

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


Notice that if you deploy your ~/.vim directory as a link (from a dotfiles repository, for example),
you must do it __before__ calling this role, which creates it if it doesn't exist.

License
-------

GPLv2

Author Information
------------------

Created by Egidio Docile
