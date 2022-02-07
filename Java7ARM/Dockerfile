# Creates image out of openjdk 11 and transform it for java 7
FROM openjdk:11-jre-slim

ADD jdk-7u60-linux-arm-vfp-hflt.tar.gz /opt

RUN ln -s /opt/jdk1.7.0_60 /opt/jdk

RUN apt-get update && apt-get upgrade -qy && apt-get clean

RUN apt-get install gcc-arm-linux-gnueabihf -qy && apt-get clean

RUN ln -s /usr/arm-linux-gnueabihf/lib/ld-linux.so.3 /lib/ld-linux.so.3
RUN ln -s /usr/arm-linux-gnueabihf/lib/ld-linux-armhf.so.3 /lib/ld-linux-armhf.so.3

ENV LD_LIBRARY_PATH=/usr/arm-linux-gnueabihf/lib/

ENV JAVA_HOME /opt/jdk
ENV PATH /usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/opt/jdk/bin
