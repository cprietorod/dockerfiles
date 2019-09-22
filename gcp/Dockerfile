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
    mkdir /opt/google-cloud-sdk &&\
    mkdir /opt/google-cloud-sdk/bin &&\
    ln -s /usr/bin/gcloud /opt/google-cloud-sdk/bin/ 
    
RUN apt update && \
    apt install  -y apt-transport-https     ca-certificates     curl     gnupg2     software-properties-common && \
    curl -fsSL https://download.docker.com/linux/debian/gpg | apt-key add - && \
    apt-key fingerprint 0EBFCD88 && \
    add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/debian $(lsb_release -cs) stable" && \
    apt update && \
    apt install -y docker-ce docker-ce-cli containerd.io docker-compose  && \
    rm -rf /var/lib/apt/lists/*

RUN gem install colorls

RUN npm install -g n && \
    n 10.11.0 && \
    npm install -gq gulp bower yarn

RUN pip2  install --upgrade pylint 

RUN pip3 install --upgrade virtualenv virtualenvwrapper pylint 

RUN cd /root && \
    wget https://github.com/cdr/code-server/releases/download/1.1156-vsc1.33.1/code-server1.1156-vsc1.33.1-linux-x64.tar.gz && \
    tar -xvf code-server1.1156-vsc1.33.1-linux-x64.tar.gz && \
    chmod 777 ./code-server1.1156-vsc1.33.1-linux-x64/code-server && \
    mv ./code-server1.1156-vsc1.33.1-linux-x64/code-server /usr/local/bin/  && \
    rm -rf ./code-server1.1156-vsc1.33.1-linux-x64 
