#
# docker run -p 8080:8080 -p 50000:50000 \
#   -v /data/jenkins:/var/jenkins \
#   --restart always \
#   --name jenkins
#

FROM alpine:latest
MAINTAINER Gianluca Arbezzano <gianarb92@gmail.com>

ENV JENKINS_HOME /var/jenkins
ENV JENKINS_OPTS ""
ENV JENKINS_VERSION "latest"

ARG user=jenkins
ARG group=jenkins
ARG uid=1000
ARG gid=1000

WORKDIR /opt
RUN apk add --update git openjdk8-jre ttf-dejavu \
    && rm -rf /var/cache/apk/* \
    && wget http://mirrors.jenkins-ci.org/war/${JENKINS_VERSION}/jenkins.war \
    && addgroup -g ${gid} ${group} \
    && adduser -h "$JENKINS_HOME" -u ${uid} -G ${group} -s /bin/sh -D ${user} \
    && chown ${user}:${group} "$JENKINS_HOME"
VOLUME  ${JENKINS_HOME}
EXPOSE 8080
EXPOSE 50000
USER ${user}

CMD ["java", "-jar", "/opt/jenkins.war", "$JENKINS_OPTS"]
