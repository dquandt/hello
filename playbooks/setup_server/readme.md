These playbooks are intended to run on a server maintenance machine.

See http://docs.ansible.com/ for more information.

#### App Server Provisioning

From the `playbooks` directory, run this command to set up the app server:

    ansible-playbook setup_server/server.yml

#### App Deployment

From the `playbooks` directory, run this command to deploy the app:

    ansible-playbook setup_server/production.yml
