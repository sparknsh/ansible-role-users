# Ansible Role: Users

#### Version: 1.0.0

[![](https://img.shields.io/badge/role-sparknsh.users-blue.svg)](https://galaxy.ansible.com/sparknsh/users)

Development of this project is managed in a private repository then pushed out to [GitLab](https://gitlab.com/sparknsh/ansible-role-users) and [GitHub](https://github.com/sparknsh/ansible-role-users) when we have a new version for you. If you have any issues please contact [sparknsh](https://www.sparknsh.com/contact?type=issue&name=ansible-role-users)

## Role Variables

```yaml
users_sudo: true
users_createhome: true
users_shell: /bin/bash

users_user_root:
  password:
  authorized_keys: []

users_user_list: []
  - name:
    state: present
    fullname:
    password:
    hushlogin: true
    shell: /bin/bash
    uid: 1001
    gid: 1001
    groups:
      - sudo
    sudo_options: ""
    authorized_key: ""
    authorized_keys: []
```

#### Example

```yaml
users_user_list:
  - name: test
    state: present
    fullname: Test User
    password: $6$pUX385iiiwdM3O$5/uI63MSMe56nfO3ZdXgps.EcoMsTNNbCu0CrhJi7vw53SsyXE9XiS5escBZgmvcXFpdY3oUDWXdomyz6fbnH1 # This password is "test"
    createhome: true
    hushlogin: true
    shell: /bin/bash
    uid: 1001
    gid: 1001
    groups:
      - sudo

```

## Example Playbook

```yaml
- hosts: all
  vars_files:
    - vars/main.yml
  roles:
     - { role: sparknsh.users }
```

## License

MIT

## Author Information

This role was created in 2019 by [sparknsh](https://www.sparknsh.com) at [Rebel Media, Inc.](https://www.rebelmedia.io/)
