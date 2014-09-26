ansible-module-etcd
===================

Ansible module for operating on etcd keys

**TODO:** add tests

## Deps

This module depends on the `python-etcd` and `requests` packages being
installed.  They must be installed locally, since the tasks in question
are delegated to localhost.

Be sure to add them to your `requirements.txt`:

```text
# requirements.txt
requests >= 2.4
python-etcd >= 0.3.2
```

## Example

Example playbook usage:

```yaml
---
- hosts: '{{ server }}'
  tasks:
    - name: set value in etcd
      etcd:
        state: present
        host: my-etcd-host.example.com
        port: 4001
        key: /asdf/foo/bar/baz/gorp
        value: my-foo-bar-baz-gor-server.prod.example.com
      delegate_to: localhost
      connection: local
      sudo: false
```
