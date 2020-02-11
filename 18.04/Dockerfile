FROM ubuntu:18.04

ENV HOME /root

RUN printf "Build of ptipd/uin-base-ubuntu:1.2_18.04, date: %s\n" `date -u +"%Y-%m-%dT%H:%M:%SZ"` > /etc/BUILD && \
    apt-get -y update && \
    apt-get -y dist-upgrade && \
    apt-get -y install locales git curl wget wput gpg-agent && \
    apt-get clean && \
    locale-gen id_ID && \
    locale-gen id_ID.UTF-8 && \
    update-locale && \
    rm -rf /var/lib/apt/lists/* /usr/share/doc/* /usr/share/man/* && \
    rm -f /var/log/*log var/log/apt/*log

CMD ["/bin/bash"]
