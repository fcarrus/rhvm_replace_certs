fcarrus.rhvm_replace_certs
=========

Replace the https and virtual console certificates on your RHVM instance.

Based on https://access.redhat.com/documentation/en-us/red_hat_virtualization/4.3/html/administration_guide/appe-red_hat_enterprise_virtualization_and_ssl#Replacing_the_Manager_CA_Certificate

Requirements
------------

None

Role Variables
--------------

|Variable | Use | Default 
|---------|-----|---------
|ca_file  | Contains the CA chain signing the certificate |/etc/pki/tls/certs/ipa-ca.crt
|cert_file| Contains the x509 certificate |/etc/pki/tls/certs/{{ ansible_fqdn }}.crt
|key_file | Contains the certificate key     |/etc/pki/tls/private/{{ ansible_fqdn }}.key

All files must be in PEM format.

Dependencies
------------

None

Example Playbook
----------------

```
- name: Replace RHVM certs
  hosts: rhvm.example.com
  gather_facts: false
  become: true
  roles:
  - fcarrus.rhvm_replace_certs
```


License
-------

GPL

