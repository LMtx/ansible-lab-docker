# MASTER image - used to create the master container to manage hosts

# use builded ansible_base (defined in ../base/Dockerfile) as a starting point
FROM ansible_base:latest

# install ansible package
RUN apt-get update \
    && apt-get install --no-install-recommends --no-install-suggests -y \
    ansible

# copy content of ansible directory from local disk to file system inside Docker image
COPY ansible /var/ans/

# change working directory
WORKDIR /var/ans

# generate RSA key pair to allow master to communicate with managed nodes
# default private key passphrase is '12345' (not a good idea for production environment ;)
RUN ssh-keygen -t rsa -N 12345 -C "master key" -f master_key
