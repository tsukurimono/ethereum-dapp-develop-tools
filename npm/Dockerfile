FROM node:15.9.0-alpine3.11

RUN apk add --no-cache --virtual build-dependencies \
    vim \
    python3 \
    make \
    gcc \
    musl-dev \
    git \
    g++

WORKDIR /work
RUN npm init -y
RUN npm config set unsafe-perm true
RUN npm install -g truffle
