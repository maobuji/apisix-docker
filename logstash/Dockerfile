FROM docker.elastic.co/logstash/logstash:7.8.0
# Add your logstash plugins setup here
# Example: RUN logstash-plugin install logstash-filter-json
RUN logstash-plugin install logstash-output-jdbc
RUN logstash-plugin install logstash-output-elasticsearch
RUN logstash-plugin install logstash-input-elasticsearch
#--no-verify