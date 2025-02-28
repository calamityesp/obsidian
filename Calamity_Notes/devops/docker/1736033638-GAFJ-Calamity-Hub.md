---
id: 1736033638-GAFJ
aliases:
  - Dockerfiles
tags:
  - devops
  - docker
  - docker_dockerfiles
  - docker_procedure_writing_dockerfile
---

<center>
<h1>Feature: Dockerfiles</h1>
</center>


##### Syntax Description
A Dockerfile is a text file with a series of commands that Docker uses to
build an image. It defines the base image, dependencies, configuration, and
the command to run your app.

##### Use Case
Dockerfile are used to create images for applications, ensuring consistency
in how they run across environments like development, testing, and production.

##### Basic Syntax
- **Dockerfile structure**:
  - `FROM`: Base image for your container.
  - `WORKDIR`: Set the working directory in the container.
  - `COPY`/`ADD`: Copy files into the container.
  - `RUN`: Execute a command during the build process.
  - `CMD`/`ENTRYPOINT`: Define the default command to run the container.


##### Options 
---

| Command               | Description                                  |
|-----------------------|----------------------------------------------|
| `FROM`               | Sets the base image.                         |
| `WORKDIR`            | Sets the working directory for commands.     |
| `COPY`/`ADD`         | Copies files or directories into the image.  |
| `RUN`                | Runs commands during the build process.      |
| `CMD`                | Default command to run when container starts.|
| `ENTRYPOINT`         | Main executable in the container.            |
| `EXPOSE`             | Declares the container's network port.       |
| `ENV`                | Sets environment variables.                  |
| `ARG`                | Defines build-time variables.                |
| `LABEL`              | Adds metadata (e.g., author info).           |
| `VOLUME`             | Creates a mount point for storage.           |
| `USER`               | Sets the user to run commands in the container.|
| `ONBUILD`            | Triggers for images built from this one.     |
| `HEALTHCHECK`        | Checks if the container is healthy.          |
| `SHELL`              | Changes the default shell for commands.      | 

---

##### Scenario:
>       You have a Node.js app that needs dependencies installed and should
>       run consistently in any environment. A Dockerfile automates setting
>       up the environment and ensures the app runs the same everywhere."

  __How To Implement:__
  - Create a `Dockerfile` in your app directory.
  - Add instructions like base image, dependencies, and commands.

  __Practical Example:__
```bash
# Dockerfile example for a Node.js app
FROM node:14
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 3000
CMD ["npm", "start"]
```



<center>
  <hr>
  <h2>Writing Your Docker File</h2>
  <hr>
</center>

### Purpose
This file outlines how a container will be built. Each line is a new directive
of how to change your docker container

### Additional Notes
- You should think of your containers as `cattle, not pets`

- Remember, Docker containers are supposed to be disposable. Create them then 
  throw them away.

- Each line is an instruction to change the Docker container (adding whats called
  a `layer`)

### Prerequisites
- List any software, hardware, or permissions required.
- Include version numbers or configurations if applicable.

### Most basic Dockerfile
---
```Dockerfile
# Start with the node container
FROM node:20

# Run the following command
CMD ["node", "-e", "console.log(\"hi lol\")"]
```
- `FROM node:20`: means start with the NODE container
                (container comes from another dockerfile)

- `CMD` :  Can only have ONE of these in a docker file, adding more and docker
         will only use the last one
         - this is what you want docker to do when someone runs the container

---

### Expected Outcome

### Troubleshooting


<center>
  <hr>
  <h2>Writing Production Ready Dockerfile</h2>
  <hr>
</center>

- Lets see how to build a basic node.js (javascript) dockerfile that is 
  closer to production ready. 

1. **Step 1**: Set the base image
   - Choose the starting point for your container
    - OS
    - Runtime Environment (eg. node.js)
   - Use the most stable version of your base image
     ```Dockerfile
     FROM node:16.2.0
     ```

2. **Step 2**: Set the working directory
   - Define the directory where commands will run to keep container organized
     ```dockerfile
    WORKDIR /app
     ```




<center>
  <hr>
  <h2>Possible OS's and Environments</h2>
  <hr>
</center>

### Operating System Base Images

| **Image**        | **Description**                          |
|-------------------|------------------------------------------|
| `ubuntu:20.04`   | Use for stable Linux-based applications. |
| `alpine:latest`  | Ideal for lightweight, small containers. |
| `debian:10`      | For Debian-based stable environments.    |
| `centos:7`       | For apps needing Red Hat compatibility.  |


### Environment Base Images

| **Image**                       | **Description**                              |
|----------------------------------|----------------------------------------------|
| `node:16`                       | Use for running Node.js applications.        |
| `python:3.9`                    | For Python apps or data processing scripts.  |
| `mcr.microsoft.com/dotnet/runtime:6.0` | For .NET applications.                     |
| `openjdk:11`                    | Use for Java applications needing JDK.       |
| `golang:1.16`                   | For Go-based server or CLI applications.     |
| `nginx:alpine`                  | Serve static websites or reverse proxies.    |
| `postgres:13`                   | For PostgreSQL databases.                    |
| `mysql:8.0`                     | For MySQL database applications.             |
