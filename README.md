# Ansible <!-- this role name --> role

This is an [Ansible](http://www.ansible.com) role which configures auditing on Linux
through auditd service for increseasing system security according to audit_rules.j2 template.

## Requirements

[Ansible 2.7+](http://docs.ansible.com/ansible/latest/intro_installation.html)

## Role Variables

```
audit_template_file:
```
Template file rules for configuring auditd rules.

```
audit_rules_file:
```
File name to contain the audit rules.

A list of all the default variables for this role is available in `defaults/main.yml`.

## Dependencies

- [amtega.check_platform](https://galaxy.ansible.com/amtega/check_platform)
- [amtega.proxy_client](https://galaxy.ansible.com/amtega/proxy_client)
- [amtega.packages](https://galaxy.ansible.com/amtega/packages)

## Usage

This is an example playbook:

```yaml
---
- host: all
  roles:
    - amtega.audit
```

## Testing

Test are based on vagrant virtual machines. The test outputs the rules configured for auditing.

You can run the rest with the following commands:

```shell
$ cd amtega.audit/tests
$ ansible-playbook mail.yml
```

## License

Copyright (C) 2019 AMTEGA - Xunta de Galicia

This role is free software: you can redistribute it and/or modify it under the terms of:

GNU General Public License version 3, or (at your option) any later version; or the European Union Public License, either Version 1.2 or – as soon they will be approved by the European Commission ­subsequent versions of the EUPL.

This role is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU General Public License for more details or European Union Public License for more details.

## Author Information

- Carlos Chedas Fernandez.
