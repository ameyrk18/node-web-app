# node-web-app

# Pipeline dependency check & purpose

Thi is a simple hello world node.js code base. Code base consists hello world application, unit test cases and a jenkins pipeline.  The jenkins pipeline will checkout the code base, do some unit testing pre-requisites,start unit testing, scan the code base for security vulnerabilities and finally build and push image to docker private hub. The image will be built and published to docker hub only if unit testing and security scanning results are positive or else fail the build. 

I am using mocha for unit testing and snyk for security scanning.  

PS: Read all the comments in the ci/pipeline.gdsl

# Dependences for this pipeline 
The following needs to be installed 
1. Docker
2. npm
3. snyk (https://wiki.jenkins.io/display/JENKINS/Snyk+Security+Plugin)
4. Create a snyk account (https://snyk.io/)

# Run unit tests, and security scanning locally

git clone https://github.com/ameyrk18/node-web-app.git

To execute the unit test locally

1. Install npm by running brew install npm (for windows and other OS documentation yet to come)

2. Start your unit testing by executing the below commands
    
``    npm prune # remove old packages if any``

``    npm install # install packages``

``    npm install -g pm2@latest # install process manager to start/stop node app``

``    pm2 start server.js # start your app``

``    mocha # run unit tests``

``    snyk auth # authethicate with snyk ``

``    snyk test # execute scanning of vulnerabilities``

``    pm2 stop server.js # stop your app``

# Build image locally 

``docker build -t <image-name>:<version> .``
  
