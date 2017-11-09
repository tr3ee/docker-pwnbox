# pwnbox 
# 
# @tr3e
# 
# version: 1.1
FROM tr3e/pwnbox:alpha-1.0

LABEL Description="This image is used to binary analysis e.g. reverse engineer, exploit, isolated execution"
LABEL Version="alpha-1.1"
MAINTAINER tr3e "tr3e@ur1.link"

# ----------- Configure -------------
COPY sshd_config /etc/ssh/sshd_config
#COPY start.sh /root/start.sh
#RUN chmod +x /root/start.sh

WORKDIR /root
CMD /root/start.sh