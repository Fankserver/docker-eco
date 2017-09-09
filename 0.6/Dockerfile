FROM mono:5.2

LABEL maintainer "Florian Kinder <florian.kinder@fankserver.com>"

RUN apt-get update -qq && \
    apt-get install -qqy wget unzip ca-certificates && \
    rm -rf /var/lib/apt/lists/* && \
    wget https://s3-us-west-2.amazonaws.com/eco-releases/EcoServer_v0.6.0.0-alpha-staging-cc778b68.zip -O /tmp/EcoServer.zip && \
    unzip /tmp/EcoServer.zip -d /eco/ && \
    rm /tmp/EcoServer.zip

EXPOSE 2999 3000 3001

VOLUME ["/eco/Storage", "/eco/Configs"]

WORKDIR /eco
ENTRYPOINT ["mono","/eco/EcoServer.exe","-nogui"]
