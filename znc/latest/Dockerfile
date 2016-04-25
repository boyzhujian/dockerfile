FROM alpine:latest

WORKDIR /tmp
RUN apk add --update g++ make git automake m4 cmake \
    && rm -rf /var/cache/apk/* \
    && git clone https://github.com/znc/znc.git \
    && cd znc \
    && git submodule update --init --recursive \
    && cmake . \
    && make \
    && make install
ADD ./znc.conf /sbin/.znc/configs/znc.conf
RUN chmod 777  /sbin/.znc/configs/znc.conf
USER daemon
EXPOSE 6060
CMD ["znc", "--foreground"]
