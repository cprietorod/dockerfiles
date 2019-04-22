FROM cprietorod/my-cloud-sdk-docker:latest

RUN mkdir /theia

ADD ./package.json /theia

RUN n 8 && \
cd /theia && \
yarn && \
yarn theia build && \
n 10.11.0
