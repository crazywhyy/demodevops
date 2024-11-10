# Use the official Jenkins LTS image as the base
FROM jenkins/jenkins:lts

# Switch to the root user to install packages
USER root

# Install additional packages, such as Git and Maven
RUN apt-get update && \
    apt-get install -y git maven && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Switch back to the Jenkins user
USER jenkins

# Copy a file that contains a list of plugins to be installed
COPY plugins.txt /usr/share/jenkins/ref/plugins.txt

# Install plugins from the list using jenkins-plugin-cli
RUN jenkins-plugin-cli -f /usr/share/jenkins/ref/plugins.txt

# Expose the necessary ports
EXPOSE 8080 50000

# Set the default command to run Jenkins using the correct start command
CMD ["java", "-jar", "/usr/share/jenkins/jenkins.war"]
