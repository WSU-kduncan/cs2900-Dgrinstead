

## There are a couple of different mounts when you are using docker. The first is bind mounts, and read only bind mounts

## I will start with bind mounts

* Bind Mount: When you use a bind mount, a file or directory on the host machine is mounted into a container. The file or directory is referenced by its absolute path on the host machine.


* Read-only bind mount: For some development applications, the container needs to write into the bind mount, so changes are propagated back to the Docker host. At some other times the container needs read access.


1. The first step you want to do is set your command

2. $ docker run -d \

3. -it \

--name devtest \
--mount type=bind,source="$(pwd)"/target,target=/app \
nginx:latest 
