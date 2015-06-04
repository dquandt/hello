# Hello

Deploying a basic Node.js/Express app.

### Dev Environment Setup

    git clone git@github.com:ryangallen/hello.git
    cd hello
    npm install
    DEBUG=hello:* npm start

### Deployment

#### EC2 Setup

1. Login to the AWS Console
1. On the EC2 page, click *Launch Instance*
1. Select the latest 64-bit Ubuntu Server
1. Click Review and Launch and manage settings
    * Tab 5. Tag instance tab - Add tags (name, etc...)
    * Tab 6. Configure security groups (TCP, HTTP, ...)
1. Click "Launch"
1. Select a key pair (or download a new one)
1. Ensure the permissions are set appropriately for key on your machine.

        sudo chown [username] [keyname].pem
        sudo chmod 400 [keyname].pem
1. If desired, allocate and associate an Elastic IP to the new server instance.

#### Environment Setup

1. ssh into the server
1. Update/upgrade the server packages

        sudo apt-get update && sudo apt-get upgrade
1. Optionally upgrade the Ubuntu release

        sudo do-release-upgrade
1. Install additional tools.

        sudo apt-get install git nodejs npm
        sudo npm install -g n
        sudo n stable
1. Create a deploy key and add it to the GitHub repository

        ssh-keygen -C "user@example.com" # press Enter three times to use default values for file location and password
        cat ~/.ssh/id_rsa.pub

    Copy the output and save it in the GitHub repo settings
1. Make a directory for the web app and adjust the permissions

        sudo mkdir /var/www/
        chown ubuntu /var/www
        chgrp ubuntu /var/www
        cd /var/www/
1. Clone the repository, install the dependencies.

        git clone git@github.com:ryangallen/hello.git
        cd hello
        npm install
1. If you allow port 3000 to be accessible in your EC2 security group, you can run the app to test that it works

        DEBUG=hello:* npm start
