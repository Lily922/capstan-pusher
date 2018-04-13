FROM golang AS build-env
WORKDIR /go/src
RUN go get github.com/LilyFaFa/capstan-pusher/cmd/capstan-pusher
RUN GOOS=linux GOARCH=386 go build -o /go/src/github.com/LilyFaFa/capstan-pusher/bin/capstan-pusher ./github.com/LilyFaFa/capstan-pusher/cmd/capstan-pusher/capstan-pusher.go

FROM alpine
WORKDIR /root/
COPY --from=build-env /go/src/github.com/LilyFaFa/capstan-pusher/bin/capstan-pusher /usr/local/bin/capstan-pusher
