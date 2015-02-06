# this is the base dockerfile

FROM ubuntu:14.04

MAINTAINER glorysdj glorysdj@gmail.com

# copy proxy
ADD ./apt.conf /etc/apt/

RUN apt-get update
RUN apt-get install -y nano openjdk-7-jdk

# install scala
ENV SCALA_VERSION 2.10.4
ENV SCALA_HOME /opt/scala-$SCALA_VERSION
ENV PATH $SCALA_HOME/bin:$PATH
ADD http://www.scala-lang.org/files/archive/scala-$SCALA_VERSION.tgz /
RUN (cd / && gunzip < scala-$SCALA_VERSION.tgz)|(cd /opt && tar -xvf -)
RUN rm /scala-$SCALA_VERSION.tgz

# git clone spark
ENV SPARK_VERSION 1.2.0
ENV SPARK_HOME /opt/spark-$SPARK_VERSION-bin-hadoop2.4
ENV PATH $SPARK_HOME:$PATH
ADD http://d3kbcqa49mib13.cloudfront.net/spark-$SPARK_VERSION-bin-hadoop2.4.tgz /
RUN (cd / && gunzip < spark-$SPARK_VERSION-bin-hadoop2.4.tgz)|(cd /opt && tar -xvf -)
RUN rm /spark-$SPARK_VERSION-bin-hadoop2.4.tgz

