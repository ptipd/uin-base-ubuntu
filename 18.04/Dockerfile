FROM ubuntu:18.04

RUN printf "Build of ptipd/uin-base-ubuntu:1.5_18.04, date: %s\n" `date -u +"%Y-%m-%dT%H:%M:%SZ"` > /etc/BUILD && \
    apt-get -y update && \
    DEBIAN_FRONTEND=noninteractive DEBCONF_NONINTERACTIVE_SEEN=true \
        apt-get -y install tzdata locales \
        file tree diffutils findutils multitail sqlite3 vim.tiny \
        net-tools iputils-ping socket telnet mtr-tiny curl wget wput sendemail \
        logrotate git ldap-utils gpg-agent libnet-smtp-ssl-perl && \
    apt-get clean && \
    locale-gen id_ID && \
    locale-gen id_ID.UTF-8 && \
    echo 'Asia/Jakarta' > /etc/timezone && \
    rm /etc/localtime && \
    ln -s /usr/share/zoneinfo/Asia/Jakarta /etc/localtime && \
    dpkg-reconfigure -f noninteractive tzdata && \
    update-locale && \
    echo "#\n\
alias egrep='egrep --color=auto'\n\
alias fgrep='fgrep --color=auto'\n\
alias grep='grep --color=auto'\n\
alias i='free -h'\n\
alias s='cd ..'\n\
alias p='cd -'\n\
alias l='ls -F'\n\
alias h='ls -lhF'\n\
alias a='ls -A'\n\
alias ha='ls -lhFA'\n\
alias la='ls -FA'\n\
alias ll='ls -lF'\n\
alias r='more'\n\
alias k='head'\n\
alias c='cat'\n\
alias g='grep'\n\
alias cp='cp -i'\n\
alias mv='mv -i'\n\
alias df='clear; df -h'\n\
alias du='du -csh'\n\
alias t='tail'\n\
alias tt='tail -n 0 -f'\n\
alias md='mkdir'\n\
alias rd='rmdir'\n\
alias rm='rm -i'\n\
alias mt='multitail'\n\
alias n='netstat -tul'\n\
alias nr='netstat -nr'\n\
alias nn='netstat -ntul'\n\
alias np='sudo netstat -tunpl'\n\
alias u='view'\n\
alias v='less'" > /etc/profile.d/alias.sh && \
    sed -i 's/^#force_color_prompt=yes/force_color_prompt=yes/' /root/.bashrc && \
    ln -s /etc/profile.d/alias.sh /root/.bash_aliases && \
    rm -rf /var/lib/apt/lists/* /usr/share/doc/* /usr/share/man/* && \
    rm -f /var/log/*log var/log/apt/*log

CMD ["/bin/bash"]
