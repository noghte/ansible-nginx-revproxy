ansible-role-nginx_revproxy

=========

## About

This ansible role is a fork from [pkchuyen's ansible-nginx-revproxy](https://github.com/pkchuyen/ansible-nginx-revproxy/), which forked the original [hispanico's ansible-nginx-revproxy](https://github.com/hispanico/ansible-nginx-revproxy/) .

- [View the original README file](https://github.com/hispanico/ansible-nginx-revproxy/blob/master/README.md)

## Changes with
## Installation
-----
- Install: `ansible-galaxy role install git+https://github.com/noghte/ansible-nginx-revproxy.git`
  > _To **uninstall** the role: `ansible-galaxy remove ansible-nginx-revproxy`_


Example Playbook
----------------

```yaml
  - hosts: all
    roles:
      - ansible-nginx-revproxy
    vars:
      nginx_revproxy_sites:
        default:
          ssl: false
          letsencrypt: false

        example.com:
          domains:
            - example.com
            - www.example.com
          upstreams:
            - { backend_address: 192.168.0.100, backend_port: 80 }
            - { backend_address: 192.168.0.101, backend_port: 80 }
          ssl: true
          letsencrypt: false
```

License
-------

Licensed under the GPLv3 License. See the LICENSE file for details.

Author Information
------------------

Hispanico (modified by `pkchuyen` and `noghte`)
