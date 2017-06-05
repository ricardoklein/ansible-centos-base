kleinstuff.centos-base
=========

Ansible role to configure some CentOS7 base system packages and rules.

Requirements
------------

You **SHOULD EDIT files/ssh_keys** and add your own keys, if you run this without this file, you probabli will have problems because this role configures ssh to only allow ssh key auth and no more password authentication.
@TODO: Change this to use host_vars and fail if there are at least one ssh public key configured.

Role Variables
--------------

### The machine hostname (to set its hostname)
        ansible_centos_base__hostname: localhost

### The user to be configured and used by ansible
        ansible_centos_base__username: ansible

### Default system timezone
        ansible_centos_base__timezone: 'America/Sao_Paulo'
### At least 1 ssh public key (you can use multiline to add more than one key with | )
        ansible_centos_base__authorized_key: |
            "ssh-rsa...
             ssh-rsa..."
### Sets the variable $EDITOR used by some things like "visudo" and "crontab -e"
        ansible_centos_base__text_editor: vim

### Basic set of tools to troubleshooting and use of the system
        ansible_centos_base__sysadmin_tools:
          - wget
          - git
          - rsync
          - sudo
          - telnet
          - traceroute
          - vim-enhanced
          - which
          - yum-plugin-keys
          - bind-utils
          - mlocate
          - zip
          - unzip
          - xz
          - curl
          - sysstat
          - fping
          - setroubleshoot-server
          - lsof
          - source-highlight
          - screen
          - tmux
          - htop
          - iftop
          - python-firewall

Dependencies
------------

This role has no dependencies, but remember to read the item **#Requirements** above.

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: kleinstuff.centos-phpfpm }

License
-------

GPLv3

Author Information
------------------

You can ask me anything using github issues on my project repository
