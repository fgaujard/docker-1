FROM debian:9

RUN apt-get update -y \
&& apt-get upgrade -y \
&& apt-get install wget -y \
&& apt-get install bzip2 -y \
&& apt-get install -y --no-install-recommends apt-utils

RUN useradd teamspeak \
&& su teamspeak

CMD /home/teamspeak

RUN  wget http://dl.4players.de/ts/releases/3.0.11.2/teamspeak3-server_linux-amd64-3.0.11.2.tar.gz \
&& tar -zxvf teamspeak3-server_linux-amd64-3.0.11.2.tar.gz \
&& rm teamspeak3-server_linux-amd64-3.0.11.2.tar.gz \

RUN ./teamspeak3-server_linux-amd64/ts3server_minimal_runscript.sh start

#Ouverture des ports
EXPOSE 9987/udp 10011 30033 41144

#Copie du .ini dans le dossier approprié.
WORKDIR teamspeak3-server_linux_amd64
COPY ts3server.ini /home/teamspeak/teamspeak3-server_linux_amd64/ts3server.ini

#Connexion en tant que USER teamspeak
USER teamspeak

#Execution du client TS
ENTRYPOINT [ "sh" , "ts3server_minimal_runscript.sh", "inifile=ts3server.ini" ]
