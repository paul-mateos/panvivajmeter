FROM mateosau/docker-jmeter:latest

MAINTAINER pmateos@planittesting.com <pmateos@planittesting.com>

# Expose port for jmeter master
EXPOSE 60000 22

#Install a basic SSH server
RUN yum install -y openssh-server
RUN sed -i 's|session required pam_loginuid.so|session optional pam_loginuid.so|g' /etc/pam.d/sshd
RUN mkdir -p /var/run/sshd

#Add user jenkins to image
RUN useradd -m -d /home/jenkins -s /bin/sh jenkins &&\
	echo "jenkins:jenkins" |chpasswd

CMD ["/usr/sbin/sshd", "-D"]

