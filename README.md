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

Install and configures Nginx as reverse proxy for multiple website.

|GitHub|Quality|Downloads|Galaxy|Version|
|------|-------|---------|-------|-------|
|[![CI](https://github.com/noghte/ansible-role-nginx_revproxy/actions/workflows/ci.yml/badge.svg)](https://github.com/noghte/ansible-role-nginx_revproxy/actions/workflows/ci.yml)|[![quality](https://img.shields.io/ansible/quality/53382)](https://galaxy.ansible.com/noghte/nginx_revproxy)|[![downloads](https://img.shields.io/ansible/role/d/53382)](https://galaxy.ansible.com/noghte/nginx_revproxy)|[![Galaxy](https://img.shields.io/badge/galaxy-noghte.nginx_revproxy-blue.svg)](https://galaxy.ansible.com/noghte/nginx_revproxy)|[![Version](https://img.shields.io/github/release/noghte/ansible-role-nginx_revproxy.svg)](https://github.com/noghte/ansible-role-nginx_revproxy/releases/)|



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

Hispanico
