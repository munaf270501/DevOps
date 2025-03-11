# Use Ubuntu 22.04 as the base image
FROM ubuntu:22.04

# Set maintainer info
#LABEL maintainer="Munaf Shaikh"

# Update and install necessary packages
RUN apt update -y && \
    apt install -y nginx && \
    apt clean

# Copy custom Nginx configuration (optional)
COPY nginx.conf /etc/nginx/nginx.conf

# Expose ports 80 and 443
EXPOSE 80 443

# Start Nginx in the foreground
CMD ["nginx", "-g", "daemon off;"]

