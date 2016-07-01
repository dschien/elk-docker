FROM debian:jessie

# =========================== STABLE FILEBEAT =========================
ENV FILEBEAT_VERSION 1.2.3
ENV FILEBEAT_SHA1 824c0b3dce16e3efd7b72b5799e97cc865951ade

RUN apt-get -y update
RUN apt-get -y install apt-utils apt-transport-https
RUN apt-get -y install curl
RUN curl https://packages.elasticsearch.org/GPG-KEY-elasticsearch | apt-key add -
RUN echo "deb https://packages.elastic.co/beats/apt stable main" | tee -a /etc/apt/sources.list.d/beats.list

RUN apt-get -y update
RUN apt-get -y install filebeat

ADD filebeat.yml /etc/filebeat/filebeat.yml
ADD filebeat.template.json /etc/filebeat/filebeat.template.json

RUN mkdir -p /etc/pki/tls/certs
ADD logstash-beats.crt /etc/pki/tls/certs/logstash-beats.crt

CMD ["filebeat", "-e", "-v", "-c", "/etc/filebeat/filebeat.yml"]
# ENTRYPOINT ["/usr/bin/filebeat", "-e", "-v", "-c", "/etc/filebeat/filebeat.yml"]
#ADD ./start.sh /usr/local/bin/start.sh
#RUN chmod +x /usr/local/bin/start.sh
#CMD [ "/usr/local/bin/start.sh" ]


# =========================== ALPHA FILEBEAT =========================
#ENV FILEBEAT_VERSION=5.0.0-alpha4
#
#RUN apt-get update
#RUN apt-get install wget -y
#RUN wget https://download.elastic.co/beats/filebeat/filebeat-5.0.0-alpha4-amd64.deb
#RUN dpkg -i filebeat-5.0.0-alpha4-amd64.deb
#RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
#
#ADD filebeat.5.yml /etc/filebeat/filebeat.yml
#ADD filebeat.template.json /etc/filebeat/filebeat.template.json
#
#RUN mkdir -p /etc/pki/tls/certs
#ADD logstash-beats.crt /etc/pki/tls/certs/logstash-beats.crt
#
#CMD ["/usr/share/filebeat/bin/filebeat", "-e", "-v", "-c", "/etc/filebeat/filebeat.yml", "-path.home", "/usr/share/filebeat", "-path.config", "/etc/filebeat", "-path.data", "/var/lib/filebeat", "-path.logs", "/var/log/filebeat"]


