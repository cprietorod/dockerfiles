FROM google/cloud-sdk:latest

RUN apt update && \
    apt -y upgrade google-cloud-sdk  && \
    apt -y install sudo default-libmysqlclient-dev  python-dev zlib1g-dev libjpeg-dev mysql-client && \
    apt -y install libmariadb-dev neovim zsh tmux wget && \
    apt -y install python3.7 python3-pip && \
    apt -y install python3.7-dev libssl-dev libffi-dev libxml2-dev libxslt1-dev && \
    apt -y install apt-transport-https ca-certificates curl gnupg2 software-properties-common && \
    apt -y install docker docker-compose  && \
    apt -y --no-install-recommends install rubygems build-essential ruby-dev ca-certificates ruby-sass openjdk-8-jdk  && \
    curl -sL https://deb.nodesource.com/setup_11.x | bash - &&\
    apt install -y  nodejs &&\
    apt -y autoremove &&\
    rm -rf /var/lib/apt/lists/* &&\
    mkdir /opt/google-cloud-sdk &&\
    mkdir /opt/google-cloud-sdk/bin &&\
    ln -s /usr/bin/gcloud /opt/google-cloud-sdk/bin/ &&\
    ln -s /usr/bin/gsutil /opt/google-cloud-sdk/bin/
    
RUN gem install colorls

RUN npm install -g n && \
    n 10.11.0 && \
    npm install -gq gulp bower yarn

RUN pip2  install --upgrade pylint 

RUN pip3 install --upgrade virtualenv virtualenvwrapper pylint 

RUN cd /root && \
    wget https://github.com/cdr/code-server/releases/download/2.1665-vsc1.39.2/code-server2.1665-vsc1.39.2-linux-x86_64.tar.gz && \
    tar -xvf code-server2.1665-vsc1.39.2-linux-x86_64.tar.gz && \
    chmod 777 ./code-server2.1665-vsc1.39.2-linux-x86_64/code-server && \
    mv ./code-server2.1665-vsc1.39.2-linux-x86_64/code-server /usr/local/bin/  && \
    rm -rf ./code-server2.1665-vsc1.39.2-linux-x86_64
