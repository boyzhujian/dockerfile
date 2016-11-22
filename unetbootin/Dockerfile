FROM alpine:latest 

RUN apk update && \
    apk add curl zlib && \
    curl -Ls http://launchpad.net/unetbootin/trunk/625/+download/unetbootin-linux64-625.bin > unetbootin && \
    chmod 755 unetbootin && \
    rm -rf /var/cache/apk/*

ENTRYPOINT ["./unetbootin"]
