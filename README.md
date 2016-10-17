[![Build Status](https://travis-ci.org/ronaldvaneede/ansible-role-aem.svg?branch=master)](https://travis-ci.org/ronaldvaneede/ansible-role-aem)

Role Name
=========

An Ansible role to provision Adobe Experience Manager (AEM) 6.x instances.

Requirements
------------

The AEM 6.x binaries are not included and should be added by yourself.  
Put them in the role's `/files` folder. You need a `cq5-author-nobrowser-p4502.jar` file with the default properties.

Role Variables
--------------

`aem.jarfile` string, default: `cq5-author-nobrowser-p4502.jar `  
`aem.instance.name` string, default: `author`  
`aem.instance.type` string, default: `author`  
`aem.instance.base` string, default: `/opt/aem`  
`aem.instance.user` string, default: `wcms`  
`aem.instance.group` string, default: `online`  
`aem.instance.port` string, default: `4502`  
`aem.instance.jvm.options` string, default: `-server -Djava.awt.headless=true`  
`aem.instance.jvm.memory`, string, default: `-Xmx1024m -XX:MaxPermSize=256M`  
`aem.instance.nosamplecontent` boolean, default: `true`  
`aem.instance.runmodes` string, default: `test`  
`aem.license.product` string, default: `Adobe Experience Manager`  
`aem.license.customer` string, default: `Acme`  
`aem.license.version` string, default: `6.1.0.20150507`  
`aem.license.key` string, default: `xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx`  
`aem.install.packages` array, default: `cq-6.1.0-hotfix-8872-1.0.zip`

Dependencies
------------

`williamyeh.oracle-java`, variables used: `java_version: 8`

Example Playbook
----------------
```
- hosts: servers  
  roles:  
    - { role: ronaldvaneede.aem, aem.license.customer: "Acme", aem.license.key: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" }
```

License
-------

MIT

Author Information
------------------

Name: Ronald van Eede  
Email: ronaldvaneede@gmail.com  
Website: ronaldvaneede.me  
Twitter: @ronaldvaneede
