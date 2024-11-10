FROM jenkins/inbound-agent:latest
# Switch to root user to install packages
USER root
# Install Node.js
RUN curl -fsSL https://deb.nodesource.com/setup_18.x | bash - && \
    apt-get install -y nodejs
# Switch back to the Jenkins user
USER jenkins
# Expose working directory
WORKDIR /home/jenkins