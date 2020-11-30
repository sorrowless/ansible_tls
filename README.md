# sbog/tls

[![Build Status](https://travis-ci.com/sorrowless/ansible_rbenv.svg?branch=master)](https://travis-ci.com/sorrowless/ansible_rbenv)
[![Ansible Role](https://img.shields.io/ansible/role/32852)](https://galaxy.ansible.com/sorrowless/rbenv)
[![Ansible Quality Score](https://img.shields.io/ansible/quality/32852)](https://galaxy.ansible.com/sorrowless/rbenv)
[![Ansible Role](https://img.shields.io/ansible/role/d/32852)](https://galaxy.ansible.com/sorrowless/rbenv)
[![GitHub](https://img.shields.io/github/license/sorrowless/ansible_rbenv)](https://github.com/sorrowless/ansible_rbenv/blob/master/LICENSE)

Role to work with TLS certificates

## Requirements

Ansible 2.4+

## Role Variables

Role variables can be placed to a dictionary named `tls_group` for gropu vars
and `tls_host` for host vars. Host vars will override group ones. There is an
example for group vars:

```yaml
tls_group:
  # Types: local
  type: local
  local_src_key: false
  local_src_cert: false
  target_dir: /etc/ssl_certs
  # Formats: nginx, haproxy
  target_format: nginx
  target_key_name: private.pem
  target_cert_name: fullchain.pem
  # If target_format is 'haproxy', this filename will be used
  target_bundle_name: bundle.pem
```

You can see all vars in `default/main.yml` vars file.

## Dependencies

None

## Example Playbook

```yaml
- name: Place needed TLS keypairs to the right places
  hosts: tls
  remote_user: root

  roles:
    - tls
```

## License

Apache 2.0

## Author Information

This role was created by [Stan Bogatkin](https://sbog.ru).
