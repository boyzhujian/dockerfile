FROM ubuntu:latest

RUN apt-get update
RUN apt-get install -y wget
RUN wget https://s3.amazonaws.com/get.influxdb.org/chronograf/chronograf_0.10.0_amd64.deb
RUN sudo dpkg -i chronograf_0.10.0_amd64.deb

ADD ./chronograf.toml /chronograf.toml
ADD ./run.sh ./run.sh
RUN chmod 755 ./run.sh

EXPOSE 10000

CMD ["chronograf", "-config=/chronograf.toml"]
