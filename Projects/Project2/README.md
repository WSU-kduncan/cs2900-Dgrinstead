Container Technologies

1. Docker Command-line interface (CLI)


Installation Instuctions

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
