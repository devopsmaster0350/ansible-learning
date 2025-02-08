# Use Ubuntu 24.04 as the base image
FROM ubuntu:24.04

# Install OpenSSH Server
RUN apt-get update && apt-get install -y openssh-server python3-pymysql python3 python3-pip python3-apt coreutils && rm -rf /var/lib/apt/lists/*

# Create SSH directory and start SSH service
RUN mkdir /var/run/sshd

# Set root password (change this in production)
RUN echo 'root:Passw0rd' | chpasswd

# Allow root login via SSH
RUN sed -i 's/^#\?PermitRootLogin .*/PermitRootLogin yes/' /etc/ssh/sshd_config

# Enable password authentication
RUN sed -i 's/^#\?PasswordAuthentication .*/PasswordAuthentication yes/' /etc/ssh/sshd_config

# Disable PAM login restriction
RUN sed -i 's@session\s*required\s*pam_loginuid.so@session optional pam_loginuid.so@g' /etc/pam.d/sshd

# Expose SSH port
EXPOSE 22

# Start SSH service
CMD ["/usr/sbin/sshd", "-D"]

#if any authentication issues please run below command
#ssh-keygen -f "/home/devopsmaster/.ssh/known_hosts" -R "172.17.0.2"
