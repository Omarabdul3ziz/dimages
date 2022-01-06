FROM ubuntu:20.04

ARG DEBIAN_FRONTEND=noninteractive

RUN apt update &&\
    apt upgrade -y

RUN apt install -y vim curl iputils-ping python3 openssh-server

RUN curl -sL https://deb.nodesource.com/setup_14.x  | bash - &&\
    apt -y install nodejs &&\
    npm install -g yarn

RUN mkdir -p /root/.ssh/ &&\
    chmod 700 /root/.ssh &&\
    touch /root/.ssh/authorized_keys &&\
    chmod 600 /root/.ssh/authorized_keys

COPY ./init.sh /init.sh
RUN chmod +x /init.sh

ENTRYPOINT [ "/init.sh" ]

# CMD [ "sleep infinity" ]