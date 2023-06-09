Ansible NGINX NMS-App-Protect Compiler Role
=========
This ansible role helps in installing a Configuration Management for App Protect Compiler which is a feature in NGINX Instance Manager Module. With Configuration Management for App Protect WAF, you can configure WAF security policies in a single location and push your configurations out to one, some, or all of your NGINX App Protect WAF instances. 

Requirements
------------
1. NGINX Management Suite License 
2. NGINX OSS or NGINX Plus
3. NGINX Management Suite
4. A supporting operating system and architecture

NGINX Management Suite Certificate Files
------------
Installing NMS requires the NMS certificate files to access the repository. Log in to MyF5 or follow the link in the trial activation email to download the NMS repo .crt and .key files:

- nginx-mgmt-suite-trial.key
- nginx-mgmt-suite-trial.crt

- NOTE: Be sure to rename these files to nginx-repo.key and nginx-repo.crt, respectively.

NGINX Instance
---------------
NMS requires an NGINX instance, either NGINX OSS or NGINX Plus as a frontend only. 
Main difference between using NGINX OSS or NGINX Plus depends on which Authentication Option you plan to use.

Ansible
--------
This role is developed and tested with maintained versions of Ansible core (above 2.12).

This role was developed and tested using nginxinc.nginx version 0.24.0.

When using this role, you will also need to install the following collections below. Additional information installing these collections is below in the Installation section.

ansible.posix
community.general
community.crypto
community.docker (Only required if you plan to use Molecule)
You will need to run this role as a root user using Ansible's "--become" parameter. Make sure you have set up the appropriate permissions on your target hosts.

Instructions on how to install Ansible can be found in the Ansible website.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------
travis.yml
```
---
- name: Install NGINX 
  hosts: nms_server
  become: true
  ignore_errors: true
  roles:
    - nms-nap-compiler
```
To run the playbook:
```
ansible-playbook travis.yml --become
```

Author Information
------------------

Itoro Ukpe
© F5, Inc. 2023

