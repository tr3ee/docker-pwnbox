# pwnbox 
# 
# @tr3e
# 
# version: 1.0
FROM ubuntu:16.04

LABEL Description="This image is used to binary analysis e.g. reverse engineer, exploit, isolated execution"
LABEL Version="alpha-1.0"
MAINTAINER tr3e "tr3e@ur1.link"

# ------------ Prerequisites ------------
## Reset root password
RUN echo 'root:pwn.th3.b0x?' | chpasswd
## Install some basic tools
RUN apt-get update && apt-get install -y openssh-server python python-pip inetutils-ping net-tools netcat curl wget vim unzip tar gzip git openssl software-properties-common python-software-properties lib32ncurses5 lib32z1 lib32stdc++6 

# ----------- Install pwntools ---------------
RUN apt-get install -y binutils-multiarch python2.7 python-dev libssl-dev libffi-dev build-essential
RUN pip install --upgrade pip
RUN pip install --upgrade pwntools

# ----------- Install ida-dbgsrv -------------
COPY linux_server /root/ida-dbgsrv/linux_server
COPY linux_serverx64 /root/ida-dbgsrv/linux_serverx64
RUN chmod +x /root/ida-dbgsrv/linux_server*

# ----------- Configure -------------
COPY sshd_config /etc/ssh/sshd_config
COPY start.sh /root/start.sh
RUN chmod +x /root/start.sh

# ----------- Cleanup ------------
RUN apt-get autoclean

EXPOSE 22 23946
EXPOSE 7357-8000

WORKDIR /root
CMD /root/start.sh
