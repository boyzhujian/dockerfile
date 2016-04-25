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
ENV HOME /home/user
RUN useradd --create-home --home-dir $HOME user \
    && chown -R user:user $HOME
ADD ./znc.conf $HOME/.znc/configs/znc.conf
USER user
EXPOSE 6060
CMD ["znc", "--foreground"]
