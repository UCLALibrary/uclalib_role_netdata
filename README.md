uclalib_role_netdata
=========

Ansible role to install the [Netdata](https://github.com/netdata/netdata) host monitoring system on a RHEL system.

Requirements
------------

This role requires a RHEL system with Apache HTTPD already installed/configured.

It will create an additional Apache virtual host file to access the Netdata interface on non-standard port.

After executing this role, you should be able to access the Netdata web ui at https://server_shortname.library.ucla.edu:30462

Role Variables
--------------

* `httpd_port` - defines the Apache httpd listening port that will proxy to Netdata (default set to `30462`)

* `server_shortname` - defines the apache server hostname netdata will answer on (e.g. if the FQDN is `netdata-server.library.ucla.edu`, the server_shortname is `netdata-server`)

* `netdata_ssl_config` - defines if the apache virtual host should use HTTPS (default set to `yes`)

* `netdata_restrict_access` - defines if the access to netdata should be restricted via firewalld (default set to `yes`)


Dependencies
------------

uclalib_role_apache

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```
- name: uclalib_netdata.yml
  become: yes
  become_method: sudo
  hosts: all

  roles:
    - { role: uclalib_role_netdata }
```
