# Inventory builder

Ansible role which create inventory file from in-memory inventory.

Do you have any playbook which deploy instances in to OpenStack, AWS, GCP? Or do you have any "dynamic inventory" as a playbook, which use module add_host? Will be potentially cool to have it store somewhere, right?..

## Features

### Formats

- [x] .ini
- [ ] .yaml

### Stored information

- [x] Hostname [ini]
- [x] ansible_host [ini]
- [x] groups [ini]

## Role Variables

inventory_format: [ini] default(ini)
inventory_file: Path where save inventory. default ("{{ playbook_dir }}/inventory.{{ inventory_format }})"

## Example Playbook

``` yaml
  - hosts: localhost
    pre_tasks:
      - name: Add host1
        add_host:
          name: host1
          groups: group001
          ansible_host: 1.2.3.4
    roles:
       - role: inventory-builder
         inventory_file: /tmp/example_inventory.ini }
```

## License

Apache License Version 2.0

## Author Information

Dominik Lenoch
