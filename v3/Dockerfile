# Protobuf Builder
# ================
#
# This image builds protocol buffers library from source with Go generation
# support. The builder and runner images are produced.

FROM golang:1.13.6-alpine3.11 as builder

MAINTAINER jinyf@ktkt.com

# System setup
RUN apk update && apk add git curl build-base autoconf automake libtool

# Install protoc
#https://github.com/protocolbuffers/protobuf/releases/download/v3.11.2/protoc-3.11.2-linux-x86_64.zip
ADD ./protoc-3.11.2 /protoc-3.11.2

ENV PATH="/protoc-3.11.2/bin:${PATH}"

# Install protoc-gen-go
# RUN go get github.com/golang/protobuf/protoc-gen-go

# Install protoc-gen-micro

#ENTRYPOINT ["/protoc-3.11.2/bin/protoc"]
#CMD ["--version"]


