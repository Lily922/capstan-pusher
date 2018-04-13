FROM golang:alpine as builder
ADD . /go/src
WORKDIR /go/src
RUN go get -u -v github.com/LilyFaFa/capstan-pusher
RUN GOOS=linux GOARCH=386 go build -v -o /go/src/app/capstan-pusher

FROM alpine
WORKDIR /root/
COPY --from=build-env /go/src/app/capstan-pusher /usr/local/bin/capstan-pusher

