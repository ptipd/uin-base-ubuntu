FROM ubuntu:18.04

ENV HOME /root

RUN apt-get -y update && \
    apt-get -y dist-upgrade && \
    apt-get -y install wget && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

CMD ["/bin/bash"]
