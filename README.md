rixx.dehydrated
===============

A role to manage dehydrated for letsencrypt certificates, including update hooks and the cronjob.

Requirements
------------

Any web server that will deliver the verification and use the ssl certificate will do. You can for example use 
[this playbook](https://github.com/rixx/ansible-nginx-base).

Role Variables
--------------



Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: rixx.dehydrated, x: 42 }

License
-------

BSD

Author Information
------------------

rixx <r at rixx.de>
