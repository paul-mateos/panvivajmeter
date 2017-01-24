FROM mateosau/docker-jmeter:latest

MAINTAINER pmateos@planittesting.com <pmateos@planittesting.com>

# Ports to expose
EXPOSE 50000 1099

#Application to run on starting the container

ENTRYPOINT $JMETER_HOME/bin/jmeter-server \
	-Dserver.rmi.localport=50000 \
	-Dserver_port=1099 
#	-Djava.rmi.server.hostname=172.17.0.2
