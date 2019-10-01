FROM debian:latest

RUN apt-get upgrade && apt-get update -y
RUN apt-get install vim git gcc curl valgrind zsh -y

RUN curl -L http://install.ohmyz.sh | sh
RUN curl https://raw.githubusercontent.com/reversTeam/Sublivim/master/installer.sh | sh

RUN git clone https://github.com/fgaujard/get_next_line.git

ENTRYPOINT [ "zsh" ]

#docker build -t work ./

#docker run -it --name work