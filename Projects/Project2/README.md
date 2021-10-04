Container Technologies

# Docker Command-line interface (CLI)


# Installation Instuctions

1. Open PowerShell session and install Docker-MicrosoftPackageManagement Provider

The command is Install-Module -Name DockerMsftProvider -Repository PSGallery -Force
you may be prompted to install NuGet provider. If you are type "y" 

2. Use the PackageManagement PowerShell Module to install the latest version of Docker 

The command is Install-Package -Name docker -ProviderName DockerMsftProvider

Powershell will ask you weather to trust the package source 'DockerDefault you need to type A to continue the installation

3. When the installation completes, restart the computer
The command for a force restart is Restart-Computer -Force

4. To run Docker you have to run the command 
Start-Service Docker 

5. There are also a couple of commands that you can use in the CLI to Update Docker


Check the installed version using the following command

Get-Package -Name Docker -ProviderName DockerMsftProvider


6. Find the current version using the following command

Find-Package -Name Docker -ProviderName DockerMsftProvider


7. The way that you upgrade is using the following command


Install-Package -Name Docker -ProviderName DockerMsftProvider -Update -Force






# How to PUll a container image

1. You can pull a docker image from the public registry you have to use a docker pull command

That command is going to be

# docker pull [OPTIONS] NAME[:TAG|@DIGEST]
also docker pull ubuntu as a command also



The example of the output is
[vagrant@localhost ~] $ docker pull ubuntu
Using default tag: latest
latest: Pulling from library/ubuntu
d54efb8db41d: Downloading [ =====================================>
f8b845f45a87: Download complete
