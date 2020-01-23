# Docker 

I am no expert on docker, I only install it to run **Splash**  to run **Javascript** driven website for scrape its content with **Scrapy**.  So from various search result on internet, here are some information regarding **docker** -
	

> **Docker** is basically a container engine which uses the Linux Kernel features like namespaces and control groups to create containers on top of an operating system and automates application deployment on the container. **Docker** uses Copy-on-write union file system for its backend storage




# Installing Docker in Linux Mint 19.3 Cinnamon
Docker Engine is available in Community Edition (CE) and Enterprise Edition (EE). In this guide, we will do the installation of Docker Community Edition on Linux Mint 19.3 using below steps.

### Uninstall old versions
Older versions of Docker were called `docker`, `docker.io`, or `docker-engine`. If these are installed, uninstall them:
```
sudo apt-get remove docker docker-engine docker.io containerd runc
```
#### SET UP THE REPOSITORY
```
sudo apt-get update
```
Install packages to allow `apt` to use a repository over HTTPS:
```
sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common
```
Add Docker’s official GPG key:
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```
Verify that you now have the key with the fingerprint `9DC8 5822 9FC7 DD38 854A E2D8 8D81 803C 0EBF CD88`, by searching for the last 8 characters of the fingerprint.
```
sudo apt-key fingerprint 0EBFCD88
    
pub   rsa4096 2017-02-22 [SCEA]
      9DC8 5822 9FC7 DD38 854A  E2D8 8D81 803C 0EBF CD88
uid           [ unknown] Docker Release (CE deb) <docker@docker.com>
sub   rsa4096 2017-02-22 [S]
```



Use the following command to set up the **stable** repository:
```
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(. /etc/os-release; echo "$UBUNTU_CODENAME") stable"

```
Update the repository:
```
sudo apt-get update
```
Install Docker:
```
sudo apt-get -y  install docker-ce docker-compose
```

# Install Splash using Docker
Pull the image:

	sudo docker pull scrapinghub/splash

Run the container:

	sudo docker run -it -p 8050:8050 --rm scrapinghub/splash





<!--stackedit_data:
eyJoaXN0b3J5IjpbLTk4MzMxMDU0OCwtOTAwNzk2NDIwLC0yNz
I3NDYwNjAsMzMwNjI2NTY0LC0xMDU1MzQyNzE5LC0yMDU3Njc5
MzYyLDY0MDAxOTkxNiwxNjE2MjY4ODIyLDExODEzMzQwNiwtMT
M2NTAxMzc4MSwxMjQ2NzYzNDk2LDMxNTM3MjUyMCwtMjA4ODc0
NjYxMl19
-->