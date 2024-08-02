# Setting Up Apache2 on Alpine Linux Docker Container

This guide walks you through setting up Apache2 on an Alpine Linux Docker container.

## Prerequisites

- Docker installed on your machine
- Basic knowledge of Docker and Alpine Linux

## Steps

### 1. Create a Dockerfile

Create a new directory for your project and navigate into it:

```sh
mkdir apache2-alpine
cd apache2-alpine

Here you have to create a Dockerfile with this content

# Use the official Alpine image as the base image
FROM alpine:latest

# Install Apache2
RUN apk update && apk add apache2

# Create the necessary directory for the web server content
RUN mkdir -p /var/www/localhost/htdocs

# Copy a simple index.html file to the Apache default directory
RUN echo "Hello from apache server" > /var/www/localhost/htdocs/index.html

# Expose port 80
EXPOSE 80

# Start Apache2 in the foreground
CMD ["httpd", "-D", "FOREGROUND"]

After this you have to build the docker-image by running command in the same directory.

#docker build -t apache2-alpine .

After this You have to run the container

#docker run --name apache-webserver -d -p 8080:80 apache2-alpine

After this you can easily check your container is running or not by this command

#docker ps
#docker ps -a

Now simply go inside the container

#docker exec -it apache-webserver /bin/ash

You are now inside the container

you have curl the localhost

#curl localhost

if /bin/ash didnot recognised curl then you have to install it

#apk add curl

This will show you that your server finally running successfully.
