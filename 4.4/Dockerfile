# VERSION 4.4.0
# AUTHOR:         Nicolas Lamirault <nicolas.lamirault@gmail.com>
# DESCRIPTION:    portefaix/kibana

FROM portefaix/base:3.3
MAINTAINER Nicolas Lamirault <nicolas.lamirault@gmail.com>

# Kibana version
ENV KIBANA_VERSION=4.4.0

RUN apk add --update curl ca-certificates

# Install NodeJS
RUN apk add --update nodejs

RUN curl -LO https://download.elasticsearch.org/kibana/kibana/kibana-${KIBANA_VERSION}-linux-x64.tar.gz && \
    tar xzf /kibana-${KIBANA_VERSION}-linux-x64.tar.gz -C /usr/share/ && \
    mv /usr/share/kibana-${KIBANA_VERSION}-linux-x64 /usr/share/kibana && \
    rm /usr/share/kibana/node/bin/node && \
    rm /usr/share/kibana/node/bin/npm && \
    ln -s /usr/bin/node /usr/share/kibana/node/bin/node && \
    ln -s /usr/bin/npm /usr/share/kibana/node/bin/npm && \
    rm -rf /var/cache/apk/* /kibana-${KIBANA_VERSION}-linux-x64.tar.gz

COPY kibana.yml /usr/share/kibana/config/kibana.yml
COPY docker-entrypoint.sh /usr/share/kibana/docker-entrypoint.sh
RUN chmod +x /usr/share/kibana/docker-entrypoint.sh

RUN curl -o /usr/local/bin/gosu -sSL "https://github.com/tianon/gosu/releases/download/1.2/gosu-amd64" && \
    chmod +x /usr/local/bin/gosu


RUN apk del curl ca-certificates && \
    rm -fr /tmp/* /var/cache/apk/*

EXPOSE 5601

ENTRYPOINT ["/usr/share/kibana/docker-entrypoint.sh"]
CMD ["kibana", "-c", "/usr/share/kibana/config/kibana.yml"]
