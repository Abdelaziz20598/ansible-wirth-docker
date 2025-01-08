# ubuntu-docker-image-with-ssh
Creating a docker image with ssh and trying to connect to it using ansible and installing some packages like nginx, note that the restart service of the nginx won't work as it is just a container not server so the service (systemctl doesn't exist) may work unexpextedly

the update here is that i am using env variables
