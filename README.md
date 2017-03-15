Security
=========

Ansible role to perform the "first 5 minute tasks" done on every server.

Tasks:

- Create deployment user
  
  - Has no password and can only be accessed through SSH.
  - User is added to sudoers.

Requirements
------------

There are no additional requirements.

Role Variables
--------------

Listed below are all the configuration options for the role along with their defaults.

```
deploy_user: 'deploy'
deploy_user_shell: '/bin/bash'
```

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

MIT

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
