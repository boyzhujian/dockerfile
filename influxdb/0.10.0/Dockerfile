FROM ubuntu
MAINTAINER Gianluca Arbezzano <gianarb92@gmail.com>

RUN apt-get update
RUN apt-get install -y wget

RUN wget https://s3.amazonaws.com/influxdb/influxdb_0.10.0-1_amd64.deb
RUN sudo dpkg -i influxdb_0.10.0-1_amd64.deb
RUN rm influxdb_0.10.0-1_amd64.deb

EXPOSE 8083
EXPOSE 8086

ENTRYPOINT ["influxd", "-config", "/etc/influxdb_conf.toml"]
