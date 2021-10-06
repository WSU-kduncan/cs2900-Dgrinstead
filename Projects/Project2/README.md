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

* To read the logs of a running container you have to run the docker ps command to list all of the running containers. The container id is located in the first column.

* just as a note you collect the logs using a log aggregator and you store them in a place where they will be available forever.

* it is dangerous to keep logs on the Docker host because they can build up over time and eat into your dkis space.

* this is why you should use a central location for your Docker logs and enable log rotation for your containers 



# Stopping a container
1. Pause

* You have to use the docker pause command. 
* $ docker pause <container name>

2. To restart the container you have to use this command in this format

* $ docker restart [OPTIONS] CONTAINER [CONTAINER...]

3. To resume a container you have to use this command 


* docker start 'docker ps -q -l' # restart it in the background


4. In order to stop a container you have to use this command

* $ docker stop <container name>

5. To kill a container you have to use this command

* $ docker kill [OPTIONS] CONTAINER [CONTAINER...]







# Azure

## This container technology is going to be azure

1. The first thing that you want to do is Sign into azure

* If you dont have an Azure subscription, crete a free account

2. Create a container instance

* When you are in Azure you want to select " Create a resource > Containers > Container Instances"

![image](https://user-images.githubusercontent.com/59849834/136124471-76c2b335-b534-49be-a805-8c8280a3b516.png)

* On the Basics page, enter the following values in the Resource group, Conatiner name, and container image text boxes. Leave the 
other values at their defaults, then select ok

* Resource group: Create new > myresourcegroup
* Container name: mycontainer
* Image source: Quickstart images
* container image mcr.microsoft.com/azuredocs/aci-helloworld(Linux)
![image](https://user-images.githubusercontent.com/59849834/136124853-81303db5-2fb9-4b58-88fa-571868042400.png)

* The sample linux image packages a small web app written in Node.js that is going to serves a static HTML.
* When you get to the network page you have to specify a DNS name label for your container

* Your container will be publicly reachable at <dns-name-label>.<region>.azurecontiner.io

* If you recieve a "DNS name label not available" error message, try a different DNS name label.

![image](https://user-images.githubusercontent.com/59849834/136127251-6228264e-b083-4fe6-82fa-4ec377986f69.png)

* Leave the other settings at their defaults, then select Review + create

* When the validation completes, you're shown a summary of the container's settings. Select Create to submit your container deployment request.

![image](https://user-images.githubusercontent.com/59849834/136127384-333d1acb-986c-4d63-ac9d-8b621bf02e00.png)

* When deployment starts, a notification appears to indicate the deployment is in progress. Another notification is displayed when the ocntainer group has been deployed

* Open the overview for the container group by navigationg to Resource Groups > myresourcegroup > mycontainer. Take note of the FQDN(the fully qualified domain name) of the container 
instance, as well its Status

![image](https://user-images.githubusercontent.com/59849834/136128593-2f0d2a37-4a10-40ca-9c59-554308a88f7c.png)

* Once its Status is Running, navigate to the container's FQDN in your browser

![image](https://user-images.githubusercontent.com/59849834/136128672-049d5144-7f39-4211-a0a1-97dcbba97c16.png)






# Logs and Status

* Viewing the logs for a container is helpful whne you are troubleshooting and issue with your container or that specific application it runs

* To view the container logs on Azure you go under settings, select Containers then Logs. then once you see that you should see the HTTP GET
request generated when you viewed the application in your browser

![image](https://user-images.githubusercontent.com/59849834/136131311-6256ede1-3368-468f-a2ee-69aefac04cbe.png)
.
