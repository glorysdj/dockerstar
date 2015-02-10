# this is the spark-worker dockerfile

FROM glorysdj/sparkbase:0.1

MAINTAINER glorysdj glorysdj@gmail.com

ADD ./cmd /root/cmd
RUN chmod 777 /root/cmd
ENTRYPOINT ["/root/cmd"]
