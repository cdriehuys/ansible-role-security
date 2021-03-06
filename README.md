Security
=========

Ansible role to perform the "first 5 minute tasks" done on every server.

Tasks:

- Perform a safe upgrade of all packages
- Create deployment user
  - Has no password and can only be accessed through SSH.
  - User is added to sudoers.
- Create any required groups

Requirements
------------

There are no additional requirements.

Role Variables
--------------

Listed below are all the configuration options for the role along with their defaults.

```YAML
apt_cache_time: 0

deploy_user: 'deploy'
deploy_user_shell: '/bin/bash'

# The SSH keys to assign to the deploy user. This is required as the deployment
# user has no password, so this is the only way to login.
deploy_user_public_keys: []             # Raw SSH keys
deploy_user_public_key_files: []        # Include keys using files, eg: ~/.ssh/id_rsa.pub

# These groups will be created
deploy_groups: []
```

Example Playbook
----------------

This role should be run as the root user of the remote system.

    - hosts: servers
      become: yes
      become_user: root
      remote_user: root
      roles:
         - { role: cdriehuys.ansible-role-security, deploy_user: sysadmin}

License
-------

MIT
