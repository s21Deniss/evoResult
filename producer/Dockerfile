FROM golang:1.15-alpine as builder

WORKDIR /go/src/app

RUN apk add --no-cache gcc libc-dev librdkafka-dev musl-dev

COPY . .

RUN go get -d -v

RUN GOOS=linux GOARCH=amd64 go build \
  -ldflags='-w -s -extldflags "-static"' -a \
  -tags musl \
  -o main .

FROM alpine:3.12

ENV KAFKA_TOPIC_IN="input"
ENV KAFKA_TOPIC_OUT="output"
ENV KAFKA_CONSUMER_GROUP="consumer"
ENV KAFKA_BROKER="192.168.50.100"
ENV KAFKA_replicationFactor="1"
ENV KAFKA_numParts="1"

COPY --from=builder /go/src/app/main /go/main

ENTRYPOINT [ "/go/main" ]
