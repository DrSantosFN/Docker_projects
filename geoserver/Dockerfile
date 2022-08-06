# Before Docker build:
# --------------------
# Create Dockerfile in /home/username
# Copy geoserver-bin.zip and extract to /home/username/geoserver
# Build Docker images using the Dockerfile instrucionts below (size: 975MB)

# Docker hub: https://hub.docker.com/_/debian?tab=tags&page=1&name=latest
FROM debian

LABEL maintainer="santos.fernandeznoguerol@tudublin.ie"

# Setting environment variables
ENV GEOSERVER_HOME=/opt/geoserver
ENV GEOSERVER_DATA_DIR=/opt/geoserver/data_dir

# Install packages
RUN apt-get update
RUN apt-get install default-jdk -y

# Copy Geoserver to container
WORKDIR /
ADD geoserver /opt/geoserver
RUN rm -r /opt/geoserver/data_dir/data
RUN mkdir /opt/geoserver/data_dir/data

# Exposes Geoserver port
EXPOSE 8080

# Start Geosever on container 
CMD ["bin/bash", "/opt/geoserver/bin/startup.sh"]
