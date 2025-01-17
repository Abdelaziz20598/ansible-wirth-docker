FROM jenkins/jenkins:lts

# Use root user to install dependencies
USER root

# Update package list and install necessary dependencies in one RUN command
RUN apt-get update && apt-get install -y apt-transport-https \
    ca-certificates curl gnupg2 \
    software-properties-common \ 
    && rm -rf /var/lib/apt/lists/*

#mahmoud code >> error
# RUN curl -fsSL https://download.docker.com/linux/debian/gpg | apt-key add -
# RUN add-apt-repository \
#         "deb [arch=amd64] https://download.docker.com/linux/debian \
#         $(lsb_release -cs) \
#         stable"
# RUN apt-get update && apt-get install -y docker-ce-cli 

# Add Docker’s official GPG key
RUN curl -fsSL https://download.docker.com/linux/debian/gpg | tee /etc/apt/trusted.gpg.d/docker.asc

# Add Docker’s stable repository
RUN echo "deb [arch=amd64 signed-by=/etc/apt/trusted.gpg.d/docker.asc] https://download.docker.com/linux/debian $(lsb_release -cs) stable" > /etc/apt/sources.list.d/docker.list

# Update apt sources
RUN apt-get update

# Install Docker CLI
RUN apt-get install -y docker-ce-cli
RUN groupadd docker

RUN usermod -aG docker jenkins
USER jenkins