# this is the first dockerfile

FROM ubuntu:14.04

MAINTAINER glorysdj glorysdj@gmail.com

# copy proxy
ADD ./apt.conf /etc/apt/

RUN apt-get update
RUN apt-get install -y nano git openjdk-7-jdk maven

# config maven & git
RUN git config --global http.proxy http://proxy01.cd.intel.com:911
RUN git config --global https.proxy https://proxy01.cd.intel.com:911
RUN export MAVEN_OPTS="-Xmx2g -XX:MaxPermSize=512M -XX:ReservedCodeCacheSize=512m"
RUN rm /etc/maven/settings.xml
ADD ./settings.xml /etc/maven/

# install scala
ENV SCALA_VERSION 2.10.4
ENV SCALA_HOME /opt/scala-$SCALA_VERSION
ENV PATH $SCALA_HOME/bin:$PATH
ADD http://www.scala-lang.org/files/archive/scala-$SCALA_VERSION.tgz /
RUN (cd / && gunzip < scala-$SCALA_VERSION.tgz)|(cd /opt && tar -xvf -)
RUN rm /scala-$SCALA_VERSION.tgz

# git clone spark
ENV SPARK_VERSION 1.2.0
ENV SPARK_HOME /opt/spark
ENV PATH $SPARK_HOME:$PATH
RUN git clone https://github.com/apache/spark.git $SPARK_HOME
RUN cd $SPARK_HOME && git checkout tags/v$SPARK_VERSION #&& mvn -DskipTests clean package
