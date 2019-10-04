uclalib_role_netdata
=========

Ansible role to install the [Netdata](https://github.com/netdata/netdata) host monitoring system on a RHEL system.

Requirements
------------

This role requires a RHEL system with Apache HTTPD already installed/configured.

It will created an additional virtual host file to access the Netdata interface.

Role Variables
--------------



Dependencies
------------

uclalib_role_apache

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }
