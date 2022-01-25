FROM ubuntu:20.04

# install helpers
RUN apt update && \
    apt -y install wget curl vim net-tools iputils-ping openssh-server

# install zinit
RUN wget -O /sbin/zinit https://github.com/threefoldtech/zinit/releases/download/v0.2.5/zinit && \
    chmod +x /sbin/zinit

# add the processes to zinit
RUN mkdir -p /etc/zinit
COPY ps /etc/zinit

# up zinit
ENTRYPOINT [ "/sbin/zinit", "init" ]
