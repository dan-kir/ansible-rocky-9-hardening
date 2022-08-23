ansible-rocky-9-hardening
==============================
[![Actively Maintained](https://img.shields.io/badge/Maintenance%20Level-Actively%20Maintained-green.svg)](https://gist.github.com/cheerfulstoic/d107229326a01ff0f333a1d3476e068d)


This role applies security hardening configurations to systems running
Rocky Linux 9 (Blue Onyx).
These configurations include:
* AIDE
* SELinux
* DNF Package Manager
* Auditd + LAUREL
* Fail2Ban
* Haveged
* Kernel tuning
* OpenSSH

Many of these configurations can be enabled/disabled in `defaults/main.yml`

Requirements
------------
Requires Ansible 2.10 or later. This role has only been tested on Rocky Linux 9 (Blue Onyx).


Role Variables
--------------
Settings and configurations can be found in defaults/main.yml.

Dependencies
------------
None

Example Playbook
----------------

    - hosts: all
      become: yes
      become_method: sudo
      roles:
        - ansible-rocky-9-hardening


Example Inventory
-----------------

*inventory.ini*

    [servers]
    192.168.0.11 ansible_ssh_user=admin machine_hostname=server01

*inventory.yml*

    ---
    all:
      hosts:
        192.168.0.11:
      vars:
        ansible_ssh_user: rocky
        machine_hostname: server01

References
-----------
* <https://github.com/openstack/ansible-hardening>
* <https://madaidans-insecurities.github.io/guides/linux-hardening.html>
* <https://github.com/microsoft/MSTIC-Sysmon/tree/main/linux>
* <https://www.whonix.org/wiki/Hardened_Malloc>
* <https://github.com/threathunters-io/laurel>
* <https://wiki.archlinux.org/title/Security>

License
-------
GPL-3.0 License

Author Information
------------------
This role was created by Dan Kir
