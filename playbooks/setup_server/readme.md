These playbooks are intended to run on a server maintenance machine.

#### Requirements

* ansible
* pyyaml

#### App Server Provisioning

From the `playbooks` directory, run this command to set up the app server:

    ansible-playbook setup_server/server.yml

#### App Deployment

From the `playbooks` directory, run this command to deploy the app:

    ansible-playbook setup_server/production.yml
