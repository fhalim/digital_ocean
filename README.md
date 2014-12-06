Role Name
=========

Role for spinning up VMs on Digital Ocean.

This role provisions the VM, so it should be executed locally. Uses the ansible
hosts specified to determine the VM to create on Digital Ocean.

Requirements
------------

This uses the Ansible Core [Digital Ocean](http://docs.ansible.com/digital_ocean_module.html) module, which depends on the dopy Python module.

Also requires that the environment variables `DO_CLIENT_ID` and `DO_API_KEY` for the account being provisioned be set


Role Variables
--------------

| Variable                 | Default | Description                                 |
|----------------------------------------------------------------------------------|
|digital_ocean_image_id    |6372108  |DO Image ID                                  |
|digital_ocean_size_id     |66       |DO Size ID                                   |
|digital_ocean_region_id   |4        |DO Region ID                                 |
|digital_ocean_monitor_port|22       |Port to connect to to verify machine liveness|
|digital_ocean_ssh_key_ids |-        |SSH ID to set up on the VM                   |


Dependencies
------------

- Python dopy module

Installing
----------

`sudo ansible-galaxy install fawad.digital_ocean`

Example Playbook
----------------

```yml
---
- hosts: all
vars:
digital_ocean_ssh_key_ids: 584065
connection: local
gather_facts: false
roles:
- fawad.digital_ocean
```

License
-------

BSD

Author Information
------------------

[Fawad Halim](mailto:fawad@fawad.net)
