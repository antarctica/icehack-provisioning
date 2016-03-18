# Icehack Provisioning

Provisioning steps for Icehack virtual environments.

## Requirements

* A local checkout of the 
[Icehack Infrastructure](https://stash.ceh.ac.uk/projects/ICEHACK16/repos/icehack-infrastructure/browse) project 
* Valid certificates for each instance/host provided by the
[Icehack Certificates](https://stash.ceh.ac.uk/projects/ICEHACK16/repos/icehack-certificates/browse) project

## Setup

To bring up instances in the production environment:

1. Checkout this project locally `$ git clone https://github.com/antarctica/icehack-provisioning`
2. Copy certificates and private keys to `provisioning/files/certificates/`
3. `$ cd icehack-provisioning/provisioning`
4. `ansible-galaxy install --role-file=./galaxy.yml --roles-path=./roles --force`
5. `$ ansible-playbook site-production.yml`

This project uses an Ansible dynamic inventory to determine which hosts should be configured. This inventory reads a 
Terraform state file maintained in the 
[Icehack Infrastructure](https://stash.ceh.ac.uk/projects/ICEHACK16/repos/icehack-infrastructure/browse) project using 
a symbolic link.

## Licence

Copyright 2016 NERC BAS.

Unless stated otherwise, all documentation is licensed under the Open Government License - version 3.
All code is licensed under the MIT license.

Copies of these licenses are included within this project.
