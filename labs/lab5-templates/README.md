# ubuntu-docker-image-with-ssh
Creating a docker image with ssh and trying to connect to it using ansible and installing some packages like nginx, note that the restart service of the nginx won't work as it is just a container not server so the service (systemctl doesn't exist) may work unexpextedly

and using env variables and loops

the update here is that i am using template
the diff btn template and copy that the template submit the vairables's values to use it inside the server ex index.html
