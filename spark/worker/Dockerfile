# this is the spark-worker dockerfile

FROM glorysdj/sparkbase:0.1

MAINTAINER glorysdj glorysdj@gmail.com

ENTRYPOINT $SPARK_HOME/bin/spark-class org.apache.spark.deploy.worker.Worker spark://glorysdj-node-01:17707 && /bin/bash
