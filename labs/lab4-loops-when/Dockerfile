FROM ubuntu:latest

#RUN passwd -d root
RUN useradd -m ansible
RUN echo "ansible:12345" | chpasswd


RUN apt update && apt install openssh-server -y && apt install sudo
RUN apt-get clean\
&& rm -rf /var/lib/apt/lists/*

RUN mkdir /var/run/sshd
RUN usermod -aG sudo ansible


# Disable password authentication and enable public key authentication for SSH
#RUN sed -i 's/^#PasswordAuthentication yes/PasswordAuthentication no/' /etc/ssh/sshd_config \
#   && sed -i 's/^PasswordAuthentication yes/PasswordAuthentication no/' /etc/ssh/sshd_config
    #\&& sed -i 's/^#PubkeyAuthentication yes/PubkeyAuthentication yes/' /etc/ssh/sshd_config \
    #&& sed -i 's/^PubkeyAuthentication no/PubkeyAuthentication yes/' /etc/ssh/sshd_config

#RUN sed -i 's/^#PermitEmptyPassword yes/PermitEmptyPassword no/' /etc/ssh/sshd_config \
#&& sed -i 's/^PermitEmptyPassword yes/PermitEmptyPassword no/' /etc/ssh/sshd_config

#RUN sed -i 's/^#PermitRootLogin yes/PermitRootLogin no/' /etc/ssh/sshd_config \
#&& sed -i 's/^PermitRootLogin yes/PermitRootLogin no/' /etc/ssh/sshd_config

#Ensure the SSH directory is correctly created


# Expose port 22 for SSH
EXPOSE 22

ENTRYPOINT service ssh start && bash