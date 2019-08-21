FROM debian

RUN apt-get update -y &&\
    apt-get upgrade -y &&\
    apt-get install ca-certificates wget ufw openssh-server -y

RUN cd /tmp &&\
    wget https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh

RUN bash /tmp/script.deb.sh

RUN ufw allow "WWW Full" &&\
    ufw allow OpenSSH

ENTRYPOINT [ "sh" ]

#docker build -t name:WorkStation ./

#docker run -it --name WorkStation