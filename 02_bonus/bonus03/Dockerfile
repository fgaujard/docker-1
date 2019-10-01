FROM debian

RUN apt-get update -y && apt-get upgrade -y
RUN apt-get install make gcc git -y

RUN git clone https://github.com/klange/nyancat.git

WORKDIR nyancat

RUN make

CMD ./src/nyancat

#docker build -t nyancat ./
#docker run -it nyancat