kleinstuff.centos-base
=========

Ansible role to configure some CentOS7 base system packages and rules.

Requirements
------------

It is required to set up "ansible_centos_base__authorized_keys" with at least one ssh key, multiline is allowed.
I want to change this and allow you to use a "install user" for setup and then add all your admin users.

Role Variables
--------------

### The user to be configured and used by ansible
        ansible_centos_base__username: centos

### Default system timezone
        ansible_centos_base__timezone: 'America/Sao_Paulo'

### At least 1 ssh public key (you can use multiline to add more than one key with | )
        ansible_centos_base__authorized_key: |
            "ssh-rsa...
             ssh-rsa..."

### Sets the variable $EDITOR used by some things like "visudo" and "crontab -e"
        ansible_centos_base__text_editor: vim

### Basic set of tools to troubleshooting and use of the system
       ansible_centos_base__packages:
          - git
          - rsync
          - sudo
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
          - setroubleshoot-server
          - lsof
          - htop
          - iftop
          - python-firewall
          - sudo
          - python-pip
          - python-virtualenv
          - gnupg
          - aide
          - openssl
          - rsyslog
          - logrotate 

Dependencies
------------

This role has no dependencies, but remember to read the item **#Requirements** above.

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: kleinstuff.centos-centos-base }

License
-------

GPLv3

Author Information
------------------

You can ask me anything using github issues on my project repository
