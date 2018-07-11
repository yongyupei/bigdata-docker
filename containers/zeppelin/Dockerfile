FROM apache/zeppelin:0.8.0
MAINTAINER Anton Kulaga <antonkulaga@gmail.com>

ENV SPARK_VERSION=2.3.1
ENV HADOOP_VERSION=2.7
ENV SPARK_HOME=/spark

ADD https://raw.githubusercontent.com/guilhem/apt-get-install/master/apt-get-install /usr/bin/
RUN chmod +x /usr/bin/apt-get-install

RUN apt-get-install -y curl \
      && wget http://apache.mirror.iphh.net/spark/spark-${SPARK_VERSION}/spark-${SPARK_VERSION}-bin-hadoop${HADOOP_VERSION}.tgz \
      && tar -xvzf spark-${SPARK_VERSION}-bin-hadoop${HADOOP_VERSION}.tgz \
      && mv spark-${SPARK_VERSION}-bin-hadoop${HADOOP_VERSION} spark \
      && rm spark-${SPARK_VERSION}-bin-hadoop${HADOOP_VERSION}.tgz

RUN apt-get-install -y python3 python3-setuptools python3-pip