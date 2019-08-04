# node-web-app


# Pipeline dependency check & purpose

To run the pipeline on jenkins please make sure you have installed node.js plugin as the pipeline relies npm. If your deploying this pipeline on slaves make sure your slave has mpm, docker installed. 

This pipeline will do the following
1. Checkout the code
2. Unit testing pre-requisite which includes installing packages and starting the aapp
3. Execute unit tests
4. Security audit
5.Build image and push to repository 

# Run unit tests locally

git clone https://github.com/ameyrk18/node-web-app.git

To execute the unit test locally

1. Install npm by running brew install npm (for windows and other OS documentation yet to come)

2. Start your unit testing by executing the below commands
    
``    npm prune # remove old packages if any
    npm install # install packages
    npm install -g pm2@latest # install process manager to start/stop node app
    pm2 start server.js # start your app
    mocha # run unit tests
    pm2 stop server.js # stop your app``

# Build image locally 

``docker build -t <image-name>:<version> .``
  
