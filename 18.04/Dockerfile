FROM ubuntu:18.04

ENV HOME /root

RUN printf "Build of ptipd/uin-base-ubuntu:18.04, date: %s\n" `date -u +"%Y-%m-%dT%H:%M:%SZ"` > /etc/BUILD && \
    apt-get -y update && \
    apt-get -y dist-upgrade && \
    apt-get -y install git curl wget wput gpg-agent && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

CMD ["/bin/bash"]
