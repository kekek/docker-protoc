ARG alpine=3.11
ARG go=1.13.6

FROM golang:$go-alpine$alpine AS build

RUN set -ex && apk --update --no-cache add \
    bash \
    make \
    cmake \
    autoconf \
    automake \
    curl \
    tar \
    libtool \
    g++ \
    git \
    libstdc++ \
    ca-certificates \
    nss

RUN curl -sSL https://github.com/uber/prototool/releases/download/v1.3.0/prototool-$(uname -s)-$(uname -m) \
    -o /usr/local/bin/prototool && \
    chmod +x /usr/local/bin/prototool

# Go get go-related bins

RUN go get -u github.com/golang/protobuf/protoc-gen-go

RUN go install github.com/golang/protobuf/protoc-gen-go

# RUN go get github.com/micro/protoc-gen-micro@v0.7.2

#wget https://github.com/micro/protoc-gen-micro/releases/tag/v0.7.2

CMD ["protoc"]