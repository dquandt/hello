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
1. Set the permissions for key on your machine appropriately.
    `sudo chown [username] [keyname].pem`
    `sudo chmod 400 [keyname].pem`
1. If desired, allocate and associate an Elastic IP to the new server instance.
