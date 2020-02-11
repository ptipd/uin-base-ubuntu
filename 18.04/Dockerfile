FROM ubuntu:18.04

ENV HOME /root

RUN printf "Build of ptipd/uin-base-ubuntu:1.3_18.04, date: %s\n" `date -u +"%Y-%m-%dT%H:%M:%SZ"` > /etc/BUILD && \
    apt-get -y update && \
    apt-get -y dist-upgrade && \
    apt-get -y install locales \
        file tree diffutils findutils multitail sqlite3 vim.tiny \
        net-tools iputils-ping socket telnet mtr-tiny curl wget wput sendemail \
        logrotate git ldap-utils gpg-agent && \
    apt-get clean && \
    locale-gen id_ID && \
    locale-gen id_ID.UTF-8 && \
    update-locale && \
    rm -rf /var/lib/apt/lists/* /usr/share/doc/* /usr/share/man/* && \
    rm -f /var/log/*log var/log/apt/*log

CMD ["/bin/bash"]
