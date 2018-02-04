FROM java:8-jre-alpine

ENV EMBULK_VERSION=0.9.0

RUN apk --update add tzdata curl && \
    cp /usr/share/zoneinfo/Asia/Tokyo /etc/localtime && \
    curl --create-dirs -o /bin/embulk -L https://dl.bintray.com/embulk/maven/embulk-${EMBULK_VERSION}.jar && \
    chmod +x /bin/embulk && \
    rm -rf /var/lib/apt/lists/* && \
    rm /var/cache/apk/* && \
    apk del curl

ENTRYPOINT ["embulk"]
