FROM alpine:edge

# We have to upgrade musl, or rspamd will not work.
RUN echo 'http://dl-cdn.alpinelinux.org/alpine/edge/testing' >> /etc/apk/repositories \
 && apk add --no-cache rspamd rsyslog ca-certificates \
 && update-ca-certificates

RUN mkdir /run/rspamd

COPY conf/ /etc/rspamd
COPY start.sh /start.sh

CMD ["/start.sh"]
