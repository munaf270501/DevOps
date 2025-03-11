# Use the official MySQL image
FROM mysql:latest

# Set environment variables
ENV MYSQL_ROOT_PASSWORD=root
ENV MYSQL_DATABASE=testdb
ENV MYSQL_USER=user
ENV MYSQL_PASSWORD=1

# Ensure correct ownership and permissions
RUN rm -rf /var/lib/mysql && \
    mkdir -p /var/lib/mysql /var/run/mysqld && \
    chown -R mysql:mysql /var/lib/mysql /var/run/mysqld && \
    chmod -R 755 /var/lib/mysql /var/run/mysqld

# Expose MySQL port
EXPOSE 3306

# Set MySQL to run as the correct user
USER mysql

# Start MySQL server
CMD ["mysqld"]

