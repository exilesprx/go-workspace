FROM golang:latest

ARG PUID=1000
ARG PGID=1000

ENV PUID ${PUID}
ENV PGID ${PGID}

RUN groupadd -g ${PGID} workspace && \
    useradd -u ${PUID} -g workspace -m workspace

ENV GOBIN=$GOPATH/bin

RUN curl https://raw.githubusercontent.com/golang/dep/master/install.sh | sh

ARG APP_DIR=
ENV APP_DIR ${APP_DIR}

ARG PORT=1323
ENV PORT ${PORT}

WORKDIR $GOPATH/src/${APP_DIR}

EXPOSE ${PORT}