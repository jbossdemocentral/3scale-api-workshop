# Installation

We provide an ansible playbook to install all the required components and software for this workshop.

Clone this repo and execute the playbook from an ansible enabled host system.

```
ansible-playbook -i ansible/inventory/workshop.inventory ansible/playbooks/openshift/install.yml 
```