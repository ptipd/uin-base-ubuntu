FROM ubuntu:18.04

ENV HOME /root

RUN printf "Build of ptipd/uin-base-ubuntu:1.1_18.04, date: %s\n" `date -u +"%Y-%m-%dT%H:%M:%SZ"` > /etc/BUILD && \
    apt-get -y update && \
    apt-get -y dist-upgrade && \
    apt-get -y install git curl wget wput gpg-agent && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* /usr/share/doc/* /usr/share/man/* && \
    rm -f /var/log/*log /var/log/apache2/*log var/log/apt/*log

CMD ["/bin/bash"]
