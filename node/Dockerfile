FROM node:10.15.0-stretch

RUN apt-get update && apt-get install -y --no-install-recommends \
rubygems build-essential ruby-dev ca-certificates ruby-sass openjdk-8-jdk \
&& rm -rf /var/lib/apt/lists/*

# Install Gulp & Bower
RUN npm install -gq gulp bower && \ 
    npm install -gq natives@1.1.6

RUN mkdir -p /tmp/workdir

WORKDIR /tmp/workdir