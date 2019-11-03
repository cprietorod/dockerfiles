FROM node:10.15.1

# Install VS Code's deps. These are the only two it seems we need.
RUN apt-get update && apt-get install -y \
	libxkbfile-dev \
	libsecret-1-dev
vgfghjgghhhh
# Ensure latest yarn.
RUN npm install -g yarn@1.13 
RUN mkdir /src && \ 
    cd /src && \
    git clone https://github.com/codercom/code-server.git && \
    cd /src/code-server && \
    yarn && NODE_ENV=production yarn task build:server:binary

# We deploy with ubuntu so that devs have a familiar environment.
FROM cprietorod/my-cloud-sdk-docker:latest

RUN apt-get update && apt-get install -y \
	locales \
	dumb-init 

RUN locale-gen en_US.UTF-8
# We unfortunately cannot use update-locale because docker will not use the env variables
# configured in /etc/default/locale so we need to set it manually.
ENV LC_ALL=en_US.UTF-8



COPY --from=0 /src/code-server/packages/server/cli-linux-x64 /usr/local/bin/code-server
EXPOSE 8443

ENTRYPOINT ["dumb-init", "code-server"]