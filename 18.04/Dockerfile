FROM ubuntu:18.04

ENV HOME /root

RUN apt-get -y update && \
    apt-get -y dist-upgrade && \
    apt-get -y install git curl wget wput gpg-agent && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

CMD ["/bin/bash"]
