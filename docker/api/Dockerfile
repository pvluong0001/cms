# ---- Base Node ----
FROM node:14.4.0-alpine3.10

RUN apk update && apk add yarn
RUN yarn global add nodemon

# Create app directory
RUN mkdir /api
WORKDIR /api

COPY entrypoint.sh /entrypoint.sh
RUN sed -i 's/\r$//' /entrypoint.sh

EXPOSE 81
