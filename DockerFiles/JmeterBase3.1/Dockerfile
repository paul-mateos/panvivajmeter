FROM mateosau/docker-java:latest

MAINTAINER pmateos@planittesting.com <pmateos@planittesting.com>

# Set Jmeter Home
ENV JMETER_HOME /jmeter/apache-jmeter-3.1/

# Add Jmeter to the Path
ENV PATH $JMETER_HOME/bin:$PATH


# Install unzip
RUN yum install -y zip unzip

# Install jmeter 3.1
RUN mkdir /jmeter \
    	&& cd /jmeter/ \
    	&& wget https://archive.apache.org/dist/jmeter/binaries/apache-jmeter-3.1.tgz \
      	&& tar -xzf apache-jmeter-3.1.tgz \
      	&& rm apache-jmeter-3.1.tgz \
	&& cd apache-jmeter-3.1

# Install jmeter plug ins

# Custom Thread Groups 2.1
RUN wget https://jmeter-plugins.org/files/packages/jpgc-casutg-2.1.zip \
	&& unzip -n jpgc-casutg-2.1.zip -d $JMETER_HOME \
	&& rm jpgc-casutg-2.1.zip

# Thoughput Shaping Timer 2.0
RUN wget https://jmeter-plugins.org/files/packages/jpgc-tst-2.0.zip \
	&& unzip -n jpgc-tst-2.0.zip -d $JMETER_HOME \
	&& rm jpgc-tst-2.0.zip 


# Various Core Components
RUN wget http://central.maven.org/maven2/org/apache/jmeter/ApacheJMeter_components/3.1/ApacheJMeter_components-3.1.jar -P $JMETER_HOME/lib/ext 

# HTTP Protocol Support
RUN wget http://central.maven.org/maven2/org/apache/jmeter/ApacheJMeter_http/3.1/ApacheJMeter_http-3.1.jar -P $JMETER_HOME/lib/ext

