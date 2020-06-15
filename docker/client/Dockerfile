# develop stage
FROM node:14.4.0-alpine3.10
RUN mkdir /client
WORKDIR /client

RUN apk --no-cache add \
    g++ make python git \
    && yarn global add node-gyp \
    && rm -rf /var/cache/apk/*

COPY entrypoint.sh /entrypoint.sh
RUN sed -i 's/\r$//' /entrypoint.sh

EXPOSE 8080
