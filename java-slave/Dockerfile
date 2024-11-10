FROM jenkins/inbound-agent:latest

# Switch to root user to install packages
USER root
# Install necessary dependencies for Jenkins agent
RUN apt-get update && apt install -y openjdk-17-jdk \
    curl \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# Set Java environment variables
ENV JAVA_HOME=/usr/lib/jvm/java-17-openjdk-amd64
ENV PATH=$JAVA_HOME/bin:$PATH

# Switch back to the Jenkins user
USER jenkins
# Expose working directory
WORKDIR /home/jenkins