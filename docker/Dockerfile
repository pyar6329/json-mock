FROM golang:1.14-alpine3.11 as build-base

WORKDIR /app
RUN set -x && \
  apk add --no-cache git && \
  go get -u github.com/pyar6329/json-mock/cmd/json-mock

FROM alpine:3.11

WORKDIR /app
COPY --from=build-base /go/bin/json-mock /usr/local/bin/json-mock
COPY *.json /app/

CMD ["json-mock"]
