FROM debian:latest

RUN apt-get update && apt-get upgrade -y
RUN apt-get install aptitude curl -y
RUN aptitude install default-jre -y

EXPOSE 25565

RUN mkdir minecraft
RUN cd minecraft

RUN curl -O https://launcher.mojang.com/v1/objects/808be3869e2ca6b62378f9f4b33c946621620019/server.jar

RUN echo "eula=true" > eula.txt

CMD java -Xmx1024M -Xms1024M -jar server.jar nogui

#build it
#docker build -t minecraft ./
#run it
#docker run -it -p 25565:25565 minecraft