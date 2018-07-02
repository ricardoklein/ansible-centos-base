kleinstuff.centos-base
=========

Ansible role to configure some CentOS7 base system packages and rules.
This role was based on the awesome job by https://github.com/bau-sec/ansible-openvpn-hardened 

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

### Basic set of system packages 
       ansible_centos_base__packages:
          - git
          - sudo
          - vim-enhanced
          - which
          - yum-plugin-keys
          - mlocate
          - setroubleshoot-server
          - python-firewall
          - python-pip
          - python-virtualenv
          - gnupg
          - aide
          - openssl
          - rsyslog
          - logrotate
          - yum-cron

### Install extra packages (usefull to use in group_vars, host_vars), but empty by default.
        ansible_centos_base__packages_extra


Dependencies
------------

This role has no dependencies, but remember to read the item **#Requirements** above.

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: kleinstuff.centos-centos-base }

#ToDo
-----
 - Configure automatic tests using TravisCI
 - Allow creating more users
 - Allow optional firewalld configuration

License
-------

GPLv3

Author Information
------------------

You can ask me anything using github issues on my project repository
