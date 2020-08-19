FROM docker.elastic.co/logstash/logstash:7.8.1
USER root

RUN yum install glibc-common wget -y

RUN \
wget -O /opt/jdk-8u221-linux-x64.tar.gz https://pub.caiweiqiang.cn/jdk/jdk-8u221-linux-x64.tar.gz && \
tar -xf /opt/jdk-8u221-linux-x64.tar.gz -C /opt && \
rm -rf /opt/jdk-8u221-linux-x64.tar.gz

RUN yum -y remove java-11-openjdk-headless-11.0.7.10-4.el7_8.x86_64
RUN yum -y remove java-11-openjdk-devel-11.0.7.10-4.el7_8.x86_64
RUN yum -y remove java-11-openjdk-11.0.7.10-4.el7_8.x86_64

RUN source /etc/profile

ENV JAVA_HOME=/opt/jdk1.8.0_221
ENV PATH=$JAVA_HOME/bin:$PATH
# Add your logstash plugins setup here
# Example: RUN logstash-plugin install logstash-filter-json
# RUN yum update -y && yum install -y java-1.8.0-openjdk-devel.x86_64 which && yum clean all
RUN logstash-plugin install logstash-output-jdbc
RUN logstash-plugin install logstash-output-elasticsearch
RUN logstash-plugin install logstash-input-elasticsearch
