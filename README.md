rixx.dehydrated
===============

A role to manage dehydrated for letsencrypt certificates, including update hooks and the cronjob.

Requirements
------------

Any web server that will deliver the verification and use the ssl certificate will do. You can for example use 
[this playbook](https://github.com/rixx/ansible-nginx-base).

Role Variables
--------------

- ``dehydrated_well_known_path: /usr/share/nginx/letsencrypt``: The path served for the challenge response, will contain the ``.acme/well_known`` directory.
- ``dehydrated_ssl_services: [- nginx]``: Services to be restarted on certificate updates.
- ``dehydrated_cert_path: /etc/ssl/letsencrypt``: The path where dehydrated itself and all certificates fetched will be located.
- ``dehydrated_domains``: A list of domain lists to be requested as certificates. The first domain in each list is the primary one that will also be in the certificate file name and path. Format:

```
dehydrated_domains:
  - domains:
    - main1.de
    - www.main1.de
    - main2.de
  - domains:
    - mail.main1.de
  - domains:
    - wtf.main1.de
```


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - role: rixx.dehydrated
         - vars:
            dehydrated_domains:
              - domains:
                  - my_domain.tld

License
-------

BSD

Author Information
------------------

rixx <r at rixx.de>
