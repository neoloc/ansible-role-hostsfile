HostsFile Role
=========

This roles purpose is to configure the `/etc/hosts` files.

[![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-neoloc.hostsfile-blue.svg)](https://galaxy.ansible.com/neoloc/ansible-role-base/)

Requirements
------------

All included in ansible-base package.

Role Variables
--------------

| Variable                | Required | Default | Choices                   | Comments                                 |
|-------------------------|----------|---------|---------------------------|------------------------------------------|
| hostsfile.localhost_as_localhost  | no  | N/A     | true, false               | when true, 127.0.0.1 is 'hostsfile.fqdn hostsfile.hostname' in /etc/hosts file, else it is 'localhost' |
| hostsfile.static_hosts       | no       | N/A     | array of name/ip values   | static host records to be added to /etc/hosts  |

```yaml
hostsfile:
  fqdn: {{ long_hostname }}
  hostname: {{ short_hostname }}
  localhost_as_localhost: true
  static_hosts:
    - ip: 10.100.0.1
      name: somehost1.domain.tld somehost1
    - ip: 10.100.0.2
      name: somehost2.domain.tld somehost2
    - ip: 10.100.0.3
      name: somehost3.domain.tld somehost3
```

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: all
      roles:
         - neoloc.hostsfile

License
-------

See license.md

Author Information
------------------

[![Github](https://img.shields.io/badge/Github-neoloc-blue.svg)](https://github.com/neoloc)
