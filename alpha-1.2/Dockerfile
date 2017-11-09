# pwnbox 
# 
# @tr3e
# 
# version: 1.2
FROM tr3e/pwnbox:alpha-1.1

LABEL Description="This image is used to binary analysis e.g. reverse engineer, exploit, isolated execution"
LABEL Version="alpha-1.2"
MAINTAINER tr3e "tr3e@ur1.link"

# ----------- Install py,man,gdb,socat ----------------
RUN apt-get update && apt-get install -y python2.7 python3 python-pip man gdb socat

# ----------- Cleanup ------------
RUN apt-get autoclean

WORKDIR /root
CMD /root/start.sh
