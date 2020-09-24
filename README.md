Role Name
=========

Installes Samba server, configures krb5.conf, nsswitch.conf and smb.conf and joins to domain using `net ads join`.  



Example Playbook
----------------


```yaml
- hosts: servers
  roles:
    - role: ansible-role-samba-ad-member
      samba_krb5_domain_name: test.de
      samba_krb5_domain_name_short: test
      samba_join_username: administrator
      samba_join_password: Passw0rd
      samba_password_server: 192.168.223.10
      samba_krb5_kdc_servers: dc.test.de
      samba_idmap_uid: 10000-20000
      samba_idmap_gid: 10000-20000
      samba_shares: 
        - { name: 'share', path: '/srv/samba/share/', valid_users: '@TEST\Domänen-Admins', force_group: 'Domänen-Admins', owner: 'root' }

```

           

