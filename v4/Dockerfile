# Protobuf Builder
# ================
#
# This image builds protocol buffers library from source with Go generation
# support. The builder and runner images are produced.

FROM namely/protoc:1.26_0 as build 

# ENTRYPOINT [ "protoc", "-I/opt/include" ]

FROM golang:1.13.6-alpine3.11 as go 

MAINTAINER jinyf@ktkt.com

RUN apk update && apk add git curl build-base autoconf automake libtool

COPY --from=build /usr/local/bin/protoc /usr/local/bin/

workdir $GOPATH/src/github.com/

run mkdir -p golang micro 

RUN curl -sSL https://github.com/golang/protobuf/archive/master.zip  -o golang.master.zip && unzip golang.master.zip && mv protobuf-master  golang/protobuf

RUN curl -sSL https://github.com/kekek/old-micro-protobuf/archive/master.zip -o micro.master.zip && unzip micro.master.zip && mv old-micro-protobuf-master  micro/protobuf

RUN cd $GOPATH/src/github.com/micro/protobuf && make install

#run ls $GOPATH/bin/

VOLUME ["/project"]

workdir /project
# ADD ./proto_file/blog.proto /project/blog.proto

ENTRYPOINT [ "./entrypoint.sh"]
