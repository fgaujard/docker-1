FROM debian

RUN apt-get update && apt-get upgrade -y
RUN apt-get install golang git vim -y

RUN mkdir workdir && cd workdir
WORKDIR workdir

COPY helloworld.go /workdir/helloworld.go

ENTRYPOINT bash

# docker build -t go .
# docker run -it go