[![Build Status](https://travis-ci.org/ronaldvaneede/ansible-role-aem.svg?branch=master)](https://travis-ci.org/ronaldvaneede/ansible-role-aem)

Role Name
=========

An Ansible role to provision AEM 6.x instances.

Requirements
------------

The AEM 6.1 binaries are not included and should be added by yourself.  
Put them in the role's `/files` folder. You need a `cq5-author-nobrowser-p4502.jar` and an `aem61_sp1.zip` file.

Role Variables
--------------

`aem_role_root` string, default: `/vagrant/ansible/roles/ansible-role-aem`, should not be needed, but need this for now for local development.  
`aem.type` string, default: `author`  
`aem.home` string, default: `/opt/aem/author`  
`aem.user` string, default: `wcms`  
`aem.group` string, default: `online`  
`aem.port` string, default: `4502`  
`aem.nosamplecontent` boolean, default: `true`  
`aem.runmodes` string, default: `author,test`  
`aem.instance_name` string, default: `author`  
`aem.jar_location` string, default: `/files/cq5-author-nobrowser-p4502.jar `  
`aem.license.product` string, default: `Adobe Experience Manager`  
`aem.license.customer` string, default: `Acme`  
`aem.license.version` string, default: `6.1.0.20150507`  
`aem.license.key` string, default: `xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx`  
`aem.installpackages` array, default: `- aem61_sp1.zip`

Dependencies
------------

`playlist.java` variables used: `java_packages: ['oracle-java8-installer', 'oracle-java8-set-default']`

Example Playbook
----------------

- hosts: servers  
  roles:  
    - { role: ansible-role-aem, aem.license.customer: "Acme", aem.license.key: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" }

License
-------

MIT

Author Information
------------------

Name: Ronald van Eede  
Email: ronaldvaneede@gmail.com  
Website: ronaldvaneede.me
Twitter: @ronaldvaneede
