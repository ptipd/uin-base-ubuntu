ARG OWN_BASE
FROM ${OWN_BASE}

ARG APP_BUILD

RUN printf "Build of ${APP_BUILD}, date: %s\n" `date -u +"%Y-%m-%dT%H:%M:%SZ"` > /etc/BUILD && \
    apt-get -y update && \
    DEBIAN_FRONTEND=noninteractive DEBCONF_NONINTERACTIVE_SEEN=true \
        apt-get -y install tzdata locales \
        file tree diffutils findutils multitail dos2unix html2text csvtool jq bc \
        net-tools iputils-ping socket telnet netcat-openbsd mtr-tiny socat \
        ftp lftp curl wget wput sendemail libnet-smtp-ssl-perl rsync \
        logrotate git gpg-agent sqlite3 vim.tiny ldap-utils mysql-client && \
    wget https://downloads.rclone.org/rclone-current-linux-amd64.deb -P /var/cache/apt/archives/ && \
    dpkg -i /var/cache/apt/archives/rclone-current-linux-amd64.deb && \
    apt-get clean && \
    locale-gen id_ID && \
    locale-gen id_ID.UTF-8 && \
    echo 'Asia/Jakarta' > /etc/timezone && \
    rm /etc/localtime && \
    ln -s /usr/share/zoneinfo/Asia/Jakarta /etc/localtime && \
    dpkg-reconfigure -f noninteractive tzdata && \
    update-locale && \
    echo -e "#\n\
alias egrep='egrep --color=auto'\nalias fgrep='fgrep --color=auto'\nalias grep='grep --color=auto'\n\
alias i='free -h'\nalias df='clear; df -h'\nalias du='du -csh'\n\
alias l='ls -F'\nalias h='ls -lhF'\nalias a='ls -A'\nalias ha='ls -lhFA'\nalias la='ls -FA'\nalias ll='ls -lF'\n\
alias c='cat'\nalias k='head'\nalias r='more'\nalias g='grep'\nalias v='less'\nalias u='view'\n\
alias t='tail'\nalias tt='tail -n 0 -f'\nalias mt='multitail'\n\
alias cp='cp -i'\nalias mv='mv -i'\nalias md='mkdir'\nalias rd='rmdir'\nalias rm='rm -i'\n\
alias n='netstat -tul'\nalias nr='netstat -nr'\nalias nn='netstat -ntul'\nalias np='sudo netstat -tunpl'\n\
alias s='cd ..'\nalias p='cd -'" > /etc/profile.d/alias.sh && \
    sed -i 's/^#force_color_prompt=yes/force_color_prompt=yes/' /root/.bashrc && \
    ln -s /etc/profile.d/alias.sh /root/.bash_aliases && \
    rm -rf /var/lib/apt/lists/* /usr/share/doc/* /usr/share/man/* && \
    rm -f /var/log/*log var/log/apt/*log

CMD ["/bin/bash"]
