# flask-helloworld
## Introduction

This is a simple Python-based web application based on the Flask microframework, which displays a string of 'Hello World!' when accessed via a web browser.

## Design decisions

1.The intially provided uncontainerized code was configured to listen on the loopback interace, which is not accessible in a containerized environment, which is why a parameter of 'host=0.0.0.0' was added to the app.run command. This binds the server to all interfaces, including the one which connects the container to the host platform so that the service may be accessed.

The diagram below illustrates the basics of Docker network connectivity:

![Alt text](docker-networking.png?raw=true "Docker networking")

2. Since 5000 is a non-standard HTTP port, the exposed port is set to the default of 80 when running the container for ease of use.

## Prerequisites

In order to run the containerized version of this application locally, a copy of Docker needs to be running on your machine.

For instructions on how to install Docker, please refer to these guidelines for your operating system of choice:

https://docs.docker.com/ee/end-to-end-install/

## Container run instructions

A previously built container can be downloaded from Docker Hub, here:

docker pull lammerse/flask-helloworld

Once all files have been downloaded, run the container by executing this command:

docker run -d -p 80:5000 lammerse/flask-helloworld

To test the Flask application, use a web brower to access the following url:

http://localhost

End.
