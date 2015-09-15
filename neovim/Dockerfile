# Neovim
#
# VERSION latest

FROM ubuntu:14.10
MAINTAINER Gianluca Arbezzano <gianarb92@gmail.com>

RUN apt-get update
RUN apt-get install -y build-essential openssl curl wget cmake \
    pkg-config libtool automake unzip

WORKDIR /tmp
RUN wget https://github.com/neovim/neovim/archive/nightly.tar.gz
RUN tar -xzvf nightly.tar.gz

WORKDIR neovim-nightly

RUN make
RUN make install

WORKDIR /

VOLUME ["~/.nvimrc", "~/.nvim"]

CMD ["nvim", "-v"]
