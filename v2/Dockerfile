FROM golang:1.13.6

MAINTAINER jinyf@ktkt.com

run echo $PWD

RUN apt-get update && apt-get install -y git make autoconf automake libtool unzip

COPY ./include /usr/local/include

COPY bin/protoc bin/

run ls  /usr/local/include
run ls bin

RUN mkdir -p src/github.com/micro

COPY ./protobuf src/github.com/micro/protobuf

run ls src/github.com/micro/protobuf

# RUN go get github.com/golang/protobuf

# RUN apt-get purge -y git make autoconf automake libtool unzip && apt-get clean -y

ENTRYPOINT ["protoc"]
