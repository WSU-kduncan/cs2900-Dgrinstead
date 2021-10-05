Container Technologies

# Docker Command-line interface (CLI)


# Installation Instuctions

1. Open PowerShell session and install Docker-MicrosoftPackageManagement Provider

* The command is Install-Module -Name DockerMsftProvider -Repository PSGallery -Force
you may be prompted to install NuGet provider. If you are type "y" 

2. Use the PackageManagement PowerShell Module to install the latest version of Docker 

* The command is Install-Package -Name docker -ProviderName DockerMsftProvider

* Powershell will ask you weather to trust the package source 'DockerDefault you need to type A to continue the installation

3. When the installation completes, restart the computer
The command for a force restart is Restart-Computer -Force

4. To run Docker you have to run the command 
Start-Service Docker 

5. There are also a couple of commands that you can use in the CLI to Update Docker


* Check the installed version using the following command

* Get-Package -Name Docker -ProviderName DockerMsftProvider


6. Find the current version using the following command

* Find-Package -Name Docker -ProviderName DockerMsftProvider


7. The way that you upgrade is using the following command


* Install-Package -Name Docker -ProviderName DockerMsftProvider -Update -Force






# How to pull a container image

1. You can pull a docker image from the public registry you have to use a docker pull command

* That command is going to be

* docker pull [OPTIONS] NAME[:TAG|@DIGEST]
* also docker pull ubuntu as a command also



The example of the output is
[vagrant@localhost ~] $ docker pull ubuntu
Using default tag: latest
latest: Pulling from library/ubuntu
d54efb8db41d: Downloading [ =====================================>
f8b845f45a87: Download complete



# How to view docker images

1. You can list the image IDs of the unused docker images

$ docker image list --quiet --filter dangling=true


# Difference between initializing and running a container

* When you initialize a container you create a new container of an image, and execute the container

* When you initialize a container you are prepping the container to run. You are setting the settings and boundaries of the container. When you run it you are running the settings that you set

# Running a container

1. When you run a contaner and you enter shell mode you want to replace <container-name> with either
the container name or containter ID.

2. When the container is running in detached mode this means the Docker container runs in the background of the terminal. It does not receive input or display output If you run containers in the back-
ground you can find out their details using docker ps and then reattach your terminal to its input and output.

* Usually when you run a container in the background this means that you want a container to run while you are able to run other commands.

* When you run a container in shell this means that the SHELL instruction allows the default shell used for the shell form of commands to be overridden.




# Logs & Status

1. To check the container status you need to access the container. 

* The first thing you want to do is obtain the container ID by running the following command "docker ps"

* Access the Docker container by runnign the follwoing command: docker exec -it <container_id>  /bin/bash

2. Reading the logs of a running container

2a.To read the logs of a running container you have to run the docker ps command to list all of the running containers. The container id is located in the first column.

* just as a note you collect the logs using a log aggregator and you store them in a place where they will be available forever.

* it is dangerous to keep logs on the Docker host because they can build up over time and eat into your dkis space.

* this is why you should use a central location for your Docker logs and enable log rotation for your containers 
