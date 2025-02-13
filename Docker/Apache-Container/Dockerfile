# Dockerfile for Apache Web Server on Ubuntu 22.04

# Set the maintainer of the image for easy contact
#LABEL maintainer="Munaf Shaikh <munaf.shaikh@apmosys.com>"

# Use official Ubuntu 22.04 image as the base image
FROM ubuntu:22.04

# Set environment variables to ensure non-interactive installation
ENV DEBIAN_FRONTEND=noninteractive

# Set the timezone to Asia/Kolkata
RUN apt-get update && apt-get install -y tzdata
RUN ln -fs /usr/share/zoneinfo/Asia/Kolkata /etc/localtime \
    && dpkg-reconfigure --frontend noninteractive tzdata

# Update package list, upgrade the system and install Apache2, networking tools, and utilities
RUN apt-get update && apt-get upgrade -y && apt-get install -y \
    apache2 \
    apache2-utils \
    telnet \
    lsof \
    net-tools \
    netcat \
    iputils-ping \
    curl \
    vim \
    traceroute \
    && rm -rf /var/lib/apt/lists/*

# Enable mod_rewrite and other necessary Apache modules (optional)
RUN a2enmod rewrite

# Copy website files from the host system to Apache's default document root
COPY ./root-folder /var/www/html/

# Expose port 80 for HTTP traffic
EXPOSE 80

# Set the working directory to the Apache root
WORKDIR /var/www/html/

# Command to start Apache in the foreground (to keep the container running)
CMD ["apachectl", "-D", "FOREGROUND"]

# Clean up unnecessary files to keep the image size smaller (optional)
RUN apt-get clean


