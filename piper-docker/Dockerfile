FROM       jrottenberg/ffmpeg:4.3-ubuntu

WORKDIR    /app

RUN        apt-get update && \
           apt-get install -y software-properties-common wget

RUN        wget https://mediaarea.net/repo/deb/repo-mediaarea_1.0-13_all.deb && \
           dpkg -i repo-mediaarea_1.0-13_all.deb && \
           apt-get update && \
           apt-get -y install mediainfo wget openjdk-11-jdk unzip python

RUN        wget "http://zebulon.bok.net/Bento4/binaries/Bento4-SDK-1-5-1-629.x86_64-unknown-linux.zip" && \ 
             unzip Bento4-SDK-1-5-1-629.x86_64-unknown-linux.zip && \ 
             rm Bento4-SDK-1-5-1-629.x86_64-unknown-linux.zip && \
             mv Bento4-SDK-1-5-1-629.x86_64-unknown-linux bento4

COPY       target/piper-0.0.1-SNAPSHOT.jar /app/piper.jar
             
ENV        PATH $PATH:/app/bento4/bin

ENTRYPOINT ["java","-jar","/app/piper.jar"]

COPY       ../target/piper-0.0.1-SNAPSHOT.jar /app/piper.jar
