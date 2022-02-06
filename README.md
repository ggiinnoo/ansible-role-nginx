NGINX
=====

This role is meant as a simple nginx installer for the listed OS'es.
While being easily configurable, it allows you to overwrite the whole nginx.conf with a simple variable overwrite.

## CI Tests
[![Ansible role nginx](https://github.com/ggiinnoo/ansible-role-nginx/actions/workflows/main.yml/badge.svg)](https://github.com/ggiinnoo/ansible-role-nginx/actions/workflows/main.yml)

---

## Playbook example


```
- hosts: webservers
  vars_files:
    - vars/main.yml
  roles:
    - role: ggiinnoo.nginx
      tags: [nginx]
```

---

## Variables



````

# What release do you want. Stable or mainline | Only used during installation
nginxRedHatRelease: stable

nginxServicePort: 80
nginxServiceSecurePort: 443

# Turn of server signatures?
nginxServiceSignatures: true

# server_names_hash_bucket_size
nginxServerNameHashBucketSize: 256

nginxErrorLog: "/var/log/nginx/error.log"
nginxAccessLog: "/var/log/nginx/access.log"

nginxConfLocationDest: "/etc/nginx/nginx.conf"
nginxConfLocationSrc: "{{ role_path }}/templates/nginxRedHat.conf.j2"

````

---


## Upcomming features

- `conf.d` folder manage

---
