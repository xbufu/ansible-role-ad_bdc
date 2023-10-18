Ansible Role: Backup Domain Controller
=========

An Ansible role to set up a backup DC. Also registers the new DC as a DNS server in the specified scope. It will also delete any previous instances of the DC in the domain.

Requirements
------------

DA credentials.

Role Variables
--------------

```yml
domain_pdc: pdc01
domain_name: ad01.bufu-sec.com
domain_password: Password!
domain_admin_user: 'AD01\Administrator'
domain_admin_password: Password!
dc_name: '{{ ansible_facts.hostname }}'
dc_ip: '{{ ansible_facts.interfaces[0].ipv4.address }}'
dhcp_scope_id: 192.168.91.0
```

Dependencies
------------

None.

Example Playbook
----------------

```yml
- hosts: bdc01
  roles:
    - role: xbufu.ad_bdc
      vars:
        domain_pdc: pdc01
        domain_name: ad01.bufu-sec.com
        domain_password: Password!
        domain_admin_user: 'AD01\Administrator'
        domain_admin_password: Password!
        dc_name: '{{ ansible_facts.hostname }}'
        dc_ip: '{{ ansible_facts.interfaces[0].ipv4.address }}'
        dhcp_scope_id: 192.168.91.0
```

License
-------

MIT / BSD

Author Information
------------------

Created by xbufu.
