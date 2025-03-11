# Use Ubuntu 22.04 as base image
FROM ubuntu:22.04

# Install Java (Required for Tomcat)
RUN apt update -y && apt install -y openjdk-17-jdk wget && apt clean

# Set environment variables
ENV CATALINA_HOME /usr/local/tomcat
ENV PATH $CATALINA_HOME/bin:$PATH

# Download and extract Apache Tomcat from archive
RUN wget -O /tmp/tomcat.tar.gz https://archive.apache.org/dist/tomcat/tomcat-10/v10.1.16/bin/apache-tomcat-10.1.16.tar.gz \
    && mkdir -p $CATALINA_HOME \
    && tar xzf /tmp/tomcat.tar.gz --strip-components=1 -C $CATALINA_HOME \
    && rm /tmp/tomcat.tar.gz

# Expose Tomcat Port
EXPOSE 8080

# Start Tomcat
CMD ["catalina.sh", "run"]

