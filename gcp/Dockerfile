FROM google/cloud-sdk:latest

RUN apt update && \
    apt -y upgrade google-cloud-sdk  && \
    apt -y install default-libmysqlclient-dev neovim zsh tmux && \
    apt -y install python-dev zlib1g-dev libjpeg-dev && \
    echo 'deb http://deb.debian.org/debian buster main' >> /etc/apt/sources.list && \
    apt update && \
    apt -y install python3.7 python3-pip && \
    apt -y autoremove &&\
    apt -y install python3-dev &&\
    apt -y --no-install-recommends install rubygems build-essential ruby-dev ca-certificates ruby-sass openjdk-8-jdk  && \
    curl -sL https://deb.nodesource.com/setup_11.x | bash - &&\
    apt install -y  nodejs &&\
    rm -rf /var/lib/apt/lists/*

RUN npm install -g n && \
    n 10.11.0 && \
    npm install -gq gulp bower yarn

RUN pip2  install --upgrade pip setuptools &&  \   
pip2  install --upgrade google-cloud-automl &&     \
pip2  install --upgrade google-cloud-storage &&     \
pip2  install --upgrade google-cloud-dataflow &&     \
pip2  install --upgrade firebase-admin &&     \
pip2  install --upgrade google-api-python-client &&     \
pip2  install --upgrade oauth2client &&\
pip2 install --upgrade MySQL-python

RUN pip3  install --upgrade google-cloud-automl &&     \
pip3  install --upgrade google-cloud-storage &&     \
pip3  install --upgrade firebase-admin &&     \
pip3  install --upgrade google-api-python-client &&     \
pip3  install --upgrade oauth2client && \
cp /usr/lib/python3.7/configparser.py /usr/lib/python3.7/ConfigParser.py && \
pip3 install --upgrade MySQL-python
