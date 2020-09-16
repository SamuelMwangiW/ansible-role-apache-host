
# Ansible Role: Apache2 site
Adds an Apache site, enables it, and restarts Apache. I usually combine with samuelmwangiw.host_file to add the host to /etc/hosts

## Dependencies
None.

## Example Playbook
```
---
- hosts: workstations
  become: yes
  vars:
    hostname: laravel8.test
    document_root: /var/www/laravel8/public
    folder: laravel8
  roles:
    - samuelmwangiw.apache_host
```

If You need the hostname added to `/etc/hosts`, here is a sample playbook
```
---
- hosts: workstations
  become: yes
  vars:
    hostname: laravel8.test
    document_root: /var/www/laravel8/public
    custom_hosts:
      - host: '{{ hostname }}'
        ip: 127.0.0.1
  roles:
    - samuelmwangiw.apache_host
    - samuelmwangiw.hosts_file
```

## Support

Issues and PRs are welcome.

## Licence

GNU GPL
