kleinstuff.centos-base
=========

Ansible role to configure some CentOS7 base system packages and rules.

Requirements
------------

I suggest you to set the variable "ansible_centos_base__hostname" so you will have your hostname set up, but you can live with the default vaule "localhost".
But it is required to you to set up "ansible_centos_base__authorized_keys" with at least one ssh key, multiline is allowed.

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
