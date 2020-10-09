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

Tests are based on [molecule](https://molecule.readthedocs.io/en/latest/installation.html) with vagrant virtual machines.

Third party modules are needed for vagrant to be supported:

```shell
# Use of virtualenv is recommended
python3 -m pip install --upgrade molecule-vagrant
```

To run the tests:

```shell
cd amtega.audit

molecule test --all
```

## License

Copyright (C) 2020 AMTEGA - Xunta de Galicia

This role is free software: you can redistribute it and/or modify it under the terms of:

GNU General Public License version 3, or (at your option) any later version; or the European Union Public License, either Version 1.2 or – as soon they will be approved by the European Commission ­subsequent versions of the EUPL.

This role is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU General Public License for more details or European Union Public License for more details.

## Author Information

- Carlos Chedas Fernandez
- Juan Antonio Valiño García
