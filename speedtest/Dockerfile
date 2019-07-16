FROM dockerio.artifactory.multi.west.ch.elca-cloud.net/python:2-alpine
MAINTAINER bag

RUN mkdir -p /app/speedtest/
RUN apk add --update curl
RUN curl https://raw.githubusercontent.com/sivel/speedtest-cli/master/speedtest.py -o /app/speedtest/speedtest-cli

RUN chmod a+rw /app/speedtest/ && \
    chmod +x /app/speedtest/speedtest-cli

ADD scripts/ /app/speedtest/

ENTRYPOINT ["/app/speedtest/init_test_connection.sh"]
