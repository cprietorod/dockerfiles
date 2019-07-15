FROM google/cloud-sdk:latest

RUN apt update && \
    apt -y upgrade google-cloud-sdk  && \
    apt -y install default-libmysqlclient-dev  python-dev zlib1g-dev libjpeg-dev mysql-client && \
    echo 'deb http://deb.debian.org/debian buster main' >> /etc/apt/sources.list && \
    apt update && \
    apt -y install libmariadb-dev neovim zsh tmux wget && \
    apt -y install python3.7 python3-pip && \
    apt -y install python3.7-dev libssl-dev libffi-dev libxml2-dev libxslt1-dev && \
    apt -y --no-install-recommends install rubygems build-essential ruby-dev ca-certificates ruby-sass openjdk-8-jdk  && \
    curl -sL https://deb.nodesource.com/setup_11.x | bash - &&\
    apt install -y  nodejs &&\
    apt -y autoremove &&\
    rm -rf /var/lib/apt/lists/*

RUN gem install colorls

RUN npm install -g n && \
    n 10.11.0 && \
    npm install -gq gulp bower yarn

RUN pip2  install --upgrade pylint 

RUN pip3 install --upgrade virtualenv virtualenvwrapper pylint 

RUN cd /root && \
    wget https://github.com/codercom/code-server/releases/download/1.903-vsc1.33.1/code-server1.903-vsc1.33.1-linux-x64.tar.gz && \
    tar -xvf code-server1.903-vsc1.33.1-linux-x64.tar.gz && \
    chmod 777 ./code-server1.903-vsc1.33.1-linux-x64/code-server && \
    mv ./code-server1.903-vsc1.33.1-linux-x64/code-server /usr/local/bin/  && \
    rm -rf ./code-server1.903-vsc1.33.1-linux-x64 
