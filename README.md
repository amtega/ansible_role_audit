# Ansible audit role

This is an [Ansible](http://www.ansible.com) role which configures auditing through auditd service.

## Role Variables

A list of all the default variables for this role is available in `defaults/main.yml`.

## Example Playbook

This is an example playbook:

``` yaml
---
- name: Audit role sample
  hosts: localhost
  roles:  
    - amtega.audit
      vars:
        audit_rules:
          - file: 40-local.rules
            content:
              - rule: "-a always,exit -F arch=b64 -S adjtimex,settimeofday -F key=time-change"
                state: present

              - rule: "-a always,exit -F arch=b64 -S clock_settime -F a0=0x0 -F key=time-change"
                state: present
```

## Testing

Tests are based on vagrant virtual machines. You can setup vagrant engine quickly using the playbook `files/setup.yml` available in the role [amtega.vagrant_engine](https://galaxy.ansible.com/amtega/vagrant_engine).

Once you have vagrant, you can run the tests with the following commands:

```shell
$ cd amtega.audit/tests
$ ansible-playbook main.yml
```

## License

Copyright (C) 2019 AMTEGA - Xunta de Galicia

This role is free software: you can redistribute it and/or modify it under the terms of:

GNU General Public License version 3, or (at your option) any later version; or the European Union Public License, either Version 1.2 or – as soon they will be approved by the European Commission ­subsequent versions of the EUPL.

This role is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU General Public License for more details or European Union Public License for more details.

## Author Information

- Carlos Chedas Fernandez
- Juan Antonio Valiño García
