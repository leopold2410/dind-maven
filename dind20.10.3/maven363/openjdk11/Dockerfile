FROM docker:20.10.3-dind

RUN apk --no-cache add openjdk11 --repository=http://dl-cdn.alpinelinux.org/alpine/edge/community
RUN apk add bash vim curl wget jq docker git tar unzip bash-completion ca-certificates
RUN cd /opt && curl -sSl http://mirror.vorboss.net/apache/maven/maven-3/3.6.3/binaries/apache-maven-3.6.3-bin.tar.gz | tar -xz

ENV MAVEN_HOME "/opt/apache-maven-3.6.3"
ENV PATH "$PATH:${MAVEN_HOME}/bin"

COPY entrypoint.sh /usr/local/bin/entrypoint.sh

ENTRYPOINT ["/bin/bash", "/usr/local/bin/entrypoint.sh"]