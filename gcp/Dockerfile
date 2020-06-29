FROM debian:10-slim

RUN mkdir -p /usr/share/man/man1

RUN apt update && \
    apt -y upgrade && \
    apt -y install sudo default-libmysqlclient-dev  python-dev zlib1g-dev libjpeg-dev default-mysql-client procps  && \
    apt -y install libmariadb-dev neovim zsh tmux wget && \
    apt -y install python3.7 python3-pip && \
    apt -y install python3.7-dev libssl-dev libffi-dev libxml2-dev libxslt1-dev && \
    apt -y install apt-transport-https ca-certificates curl gnupg2 software-properties-common && \
    apt -y install docker docker-compose  && \
    apt -y --no-install-recommends install rubygems build-essential ruby-dev ca-certificates ruby-sass openjdk-11-jdk  && \
    curl -sL https://deb.nodesource.com/setup_12.x | bash - &&\
    apt install -y  nodejs &&\
    apt -y autoremove &&\
    rm -rf /var/lib/apt/lists/* 

RUN cd /opt && \
    wget https://dl.google.com/dl/cloudsdk/channels/rapid/downloads/google-cloud-sdk-293.0.0-linux-x86_64.tar.gz && \
    tar -xvf google-cloud-sdk-293.0.0-linux-x86_64.tar.gz && \
    /opt/google-cloud-sdk/install.sh --quiet && \ 
    rm -rf /opt/google-cloud-sdk-293.0.0-linux-x86_64.tar.gz && \ 
    /opt/google-cloud-sdk/bin/gcloud components update --quiet && \
    /opt/google-cloud-sdk/bin/gcloud components install app-engine-go  appctl  cbt  bigtable  datalab && \ 
    /opt/google-cloud-sdk/bin/gcloud components install cloud-datastore-emulator cloud-firestore-emulator pubsub-emulator && \ 
    /opt/google-cloud-sdk/bin/gcloud components install cloud_sql_proxy cloud-spanner-emulator emulator-reverse-proxy && \ 
    /opt/google-cloud-sdk/bin/gcloud components install cloud-build-local docker-credential-gcr kind minikube skaffold && \
    /opt/google-cloud-sdk/bin/gcloud components install anthos-auth alpha beta app-engine-java app-engine-php && \
    /opt/google-cloud-sdk/bin/gcloud components install app-engine-python app-engine-python-extras kpt kubectl bq core gsutil && \
    ln -s /opt/google-cloud-sdk/bin/* /bin/ 

RUN gem install colorls

RUN npm install -g n && \
    n 10.11.0 && \
    npm install -gq gulp bower yarn

RUN pip3 install --upgrade virtualenv virtualenvwrapper pylint 

RUN cd /root && \
    wget https://github.com/cdr/code-server/releases/download/3.4.1/code-server_3.4.1_amd64.deb && \
    dpkg -i code-server_3.4.1_amd64.deb && \
    rm -rf code-server_3.4.1_amd64.deb

