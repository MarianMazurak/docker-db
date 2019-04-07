# adding base image ubuntu
FROM ubuntu:latest
#adding maintainers of this docker
MAINTAINER Bogdan Myslyvchuk & Marian Mazurak

RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y openjdk-8-jdk \
    git \
    maven && \
    # midnight commander, to run type mc
    mc && \
    
    wget && \
    apt-get clean;
  
# Fix certificate issues
RUN apt-get update && \
    apt-get install ca-certificates-java && \
    apt-get clean && \
    update-ca-certificates -f;

# Setup JAVA_HOME -- useful for docker commandline
ENV JAVA_HOME /usr/lib/jvm/java-8-openjdk-amd64/
ENV PATH=$PATH:$JAVA_HOME/bin
RUN echo export PATH=$PATH:$JAVA_HOME/bin >> /etc/environment
