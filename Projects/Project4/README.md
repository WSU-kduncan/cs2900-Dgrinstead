# Project4

## Docker


- For Docker there are three different networking modes.

1. Bridge

2. Overlay

3. Macvlan network

- Bridged networking is a Link Layer Device which forwards traffic between network segments. In terms of Docker, a bridge network uses a software bridge which allows containers connects to the same bridge network to communicate, while providing isolation from containers which are not connected to the bridged network

- For Overlay Networking. This network driver creates a distributed network among multiple docker daemon hosts. This network sits on top of the Host-specific networks, allowing containers conected to it to communicate securely when
encryption is enabled.

- Macvlan networks. Some applications especially legacy applications or applications or applications which monitor network traffic, expect to be directly connected to the physical network.


- In docker The default networking mode is bridge. This is what happens when you dont specify a drive

- In docker to run the container and bind a host port to the container port you need to run docker run -p 127.0.0.1:80:8080/tcp ubuntu bash.



# Podman


- In podman there are three different networking types

1. Rootless networking- When using podman as a rootless user, the network is setup automatically. The container itself does not have an IP address, because without root privileges, network association is not allowed.

2. Rootful Networking- This means you are using podman as a root user. So you have more access to this technology

- Bridged network is used by default




# Vulnerability Scanners


- The linter is parsing the Dockerfile into an AST and performs rules on top of the AST - It additionally is using the
famous Shellcheck to lint the bash code inside RUN

- Try detects vulnerabilities of OS packages (Alpine, RHEL, CentOS and application dependencies(Bundler, Cpomposer, npm, yarn)


