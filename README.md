ansible-module-etcd
===================

Ansible module for operating on etcd keys

**TODO:** add tests

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

    - name: get value from etcd
      etcd:
        state: retrieved
        host: my-etcd-host.example.com
        port: 4001
        key: /asdf/foo/bar/baz/gorp
      register: foo
      delegate_to: localhost
      connection: local
      sudo: false
      register: result # use result.value
```
