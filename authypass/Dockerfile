FROM ubuntu:14.04

RUN apt-get update -y && apt-get upgrade -y && apt-get install -y curl
RUN apt-get install -y curl openssh-server && \
    curl -O 'https://raw.githubusercontent.com/authy/authy-ssh/master/authy-ssh'

ADD entrypoint.sh /usr/bin/entrypoint.sh
ADD sshd_config /etc/ssh/sshd_config
ADD set_password.sh /usr/bin/set_password.sh

RUN chmod +x /usr/bin/entrypoint.sh /usr/bin/set_password.sh
ENTRYPOINT /usr/bin/entrypoint.sh
CMD /usr/sbin/sshd -D
