# HOST image - used to create containers to be managed by master

# use builded ansible_base (defined in ../base/Dockerfile) as a starting point
FROM ansible_base:latest

# copy script from local disk to file system inside Docker image
COPY run.sh /var/

# adjust file permissions to make run.sh executable
RUN chmod 755 /var/run.sh
