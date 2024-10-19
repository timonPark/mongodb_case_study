# Base image
FROM amazonlinux:latest

# Create directories for MongoDB and config files
RUN mkdir -p /home/download /home/mongodb/config /mongodb/data1 /mongodb/data2 /mongodb/data3 /mongodb/logs

# Install wget, tar, and gzip to download and extract the MongoDB tarball
RUN yum install -y wget tar gzip

# Download MongoDB RPM file
RUN wget https://fastdl.mongodb.org/linux/mongodb-linux-x86_64-amazon2023-8.0.1.tgz \
    -O /home/download/mongodb-linux-x86_64-amazon2023-8.0.1.tgz

# Extract the downloaded MongoDB tarball to /mongodb directory
RUN tar -xvzf /home/download/mongodb-linux-x86_64-amazon2023-8.0.1.tgz -C /mongodb --strip-components=1

# Command to keep the container running (for testing)
CMD ["/bin/bash"]
