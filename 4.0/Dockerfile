# VERSION 4.0.3
# AUTHOR:         Nicolas Lamirault <nicolas.lamirault@gmail.com>
# DESCRIPTION:    portefaix/kibana

FROM portefaix/base:3.2
MAINTAINER Nicolas Lamirault <nicolas.lamirault@gmail.com>

# Kibana version
ENV KIBANA_VERSION=4.0.3

RUN apk add --update curl ca-certificates

# Install NodeJS
RUN apk add --update nodejs

RUN curl -LO https://download.elasticsearch.org/kibana/kibana/kibana-${KIBANA_VERSION}-linux-x64.tar.gz && \
    tar xzf /kibana-${KIBANA_VERSION}-linux-x64.tar.gz -C / && \
    mv /kibana-${KIBANA_VERSION}-linux-x64 /usr/share/kibana && \
    rm /usr/share/kibana/node/bin/node && \
    rm /usr/share/kibana/node/bin/npm && \
    ln -s /usr/bin/node /usr/share/kibana/node/bin/node && \
    ln -s /usr/bin/npm /usr/share/kibana/node/bin/npm && \
    rm -rf /var/cache/apk/* /kibana-${KIBANA_VERSION}-linux-x64.tar.gz
RUN sed -i '/elasticsearch_url/s/localhost/elasticsearch/' /usr/share/kibana/config/kibana.yml
RUN apk del curl ca-certificates && \
    rm -fr /tmp/* /var/cache/apk/*

EXPOSE 5601

CMD ["/usr/share/kibana/bin/kibana"]
