# adding base image ubuntu
FROM ubuntu:latest
#adding maintainers of this docker
MAINTAINER Bogdan Myslyvchuk & Marian Mazurak

RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y openjdk-8-jdk mc wget sudo\
    git \
    maven && \
    apt-get clean;
# Use the -m (--create-home) option to create the user home directory as /home/username
RUN useradd -ms /bin/bash -p $(openssl passwd -1 71191pwd) -G sudo dev
RUN mkdir /home/dev/git
RUN mkdir /home/dev/bin
RUN chown -R dev:dev /home/dev

# Fix certificate issues
RUN apt-get update && \
    apt-get install ca-certificates-java && \
    apt-get clean && \
    update-ca-certificates -f;

# Setup JAVA_HOME -- useful for docker commandline
ENV JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
ENV PATH=$PATH:$JAVA_HOME/bin
RUN echo export PATH=$PATH:$JAVA_HOME/bin >> /etc/environment

#Setup M2_HOME
ENV M2_HOME=/usr/share/maven
ENV PATH=$PATH:$M2_HOME/bin
RUN echo export PATH=$PATH:$M2_HOME/bin >> /etc/environment

