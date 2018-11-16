sbog/tls
========

Role to work with TLS certificates

#### Requirements

Ansible 2.4

#### Role Variables

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

#### Dependencies

None

#### Example Playbook

```yaml
- name: Place needed TLS keypairs to the right places
  hosts: tls
  remote_user: root

  roles:
    - tls
```

#### License

Apache 2.0

#### Author Information

Stanislaw Bogatkin (https://sbog.ru)
