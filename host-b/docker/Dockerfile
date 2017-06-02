# Get some docker image
FROM webdevops/php-apache:ubuntu-16.04

# Install keepalived on it
RUN apt-get update && apt-get install -y keepalived

# Copy keepalived configuration into correct place
COPY keepalived.conf /etc/keepalived

# Perform other necessary operations
COPY index.php /app

# Make sure keepalived will run
COPY keepalived-supervisord.conf /opt/docker/etc/supervisor.d

EXPOSE 80
