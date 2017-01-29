# golang/dep (go v1.7)
#
# docker run --rm -v $GOPATH/src:/go/src -w /go/src/github.com/your-account/project pottava/dep:go1.7 ensure

FROM alpine:3.5

ENV GOPATH=/go

WORKDIR /go/src

RUN apk --no-cache add git
RUN apk --no-cache add --virtual build-dependencies bash gcc musl-dev openssl go \

    # Install go 1.7
    && GOLANG_VERSION=1.7.5 \
    && GOLANG_SRC_URL=https://golang.org/dl/go$GOLANG_VERSION.src.tar.gz \
    && GOLANG_SRC_SHA256=4e834513a2079f8cbbd357502cccaac9507fd00a1efe672375798858ff291815 \
    && export GOROOT_BOOTSTRAP="$(go env GOROOT)" \
    && wget -q "$GOLANG_SRC_URL" -O golang.tar.gz \
    && echo "$GOLANG_SRC_SHA256  golang.tar.gz" | sha256sum -c - \
    && tar -C /usr/local -xzf golang.tar.gz \
    && wget -q https://raw.githubusercontent.com/docker-library/golang/master/1.7/alpine3.5/no-pic.patch \
    && wget -q https://raw.githubusercontent.com/docker-library/golang/master/1.7/alpine3.5/17847.patch \
    && cd /usr/local/go/src \
    && patch -p2 -i /go/src/no-pic.patch \
    && patch -p2 -i /go/src/17847.patch \
    && ./make.bash \
    && chmod -R 777 /go \

    # Compile golang/dep
    && go get -u github.com/golang/dep/... \
    && mv /go/bin/dep /usr/bin \

    # Clean up
    && apk del --purge -r build-dependencies \
    && rm -rf /usr/local/go /usr/lib/go /go \
        /var/cache/* /var/lib/apk* /usr/local/go/pkg

ENTRYPOINT ["dep"]
CMD ["-h"]
