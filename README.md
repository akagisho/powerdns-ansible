# powerdns-ansible

## requirements

* Ansible
* Vagrant (For development environment)

## setup

Clone this repository.

    $ git clone https://github.com/akagisho/powerdns-ansible.git
    $ cd powerdns-ansible

Start VMs.

    $ vagrant up

## execute

Execute ansible playbook.

### for development environment

    $ vagrant provision

### for production environment

    $ ansible-playbook -i inventories/production/hosts site.yml

## use

Access to PowerDNS-Admin.

* [http://10.200.19.10:9191/](http://10.200.19.10:9191/)