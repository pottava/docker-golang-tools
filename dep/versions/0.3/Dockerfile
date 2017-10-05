# golang/dep v0.3
#
# docker run --rm pottava/dep:0.3 --help
# docker run --rm -v $GOPATH/src:/go/src -w /go/src/github.com/your-account/project pottava/dep:0.3 ensure

FROM alpine:3.6

ENV GODEP_VERSION=v0.3.1 \
    GOPATH=/go

WORKDIR /go/src

RUN apk --no-cache add git
RUN apk --no-cache add --virtual build-dependencies bash gcc musl-dev openssl go \

    # Install go 1.9
    && GOLANG_VERSION=1.9.1 \
    && GOLANG_SRC_URL=https://golang.org/dl/go$GOLANG_VERSION.src.tar.gz \
    && GOLANG_SRC_SHA256=a84afc9dc7d64fe0fa84d4d735e2ece23831a22117b50dafc75c1484f1cb550e \
    && export GOROOT_BOOTSTRAP="$(go env GOROOT)" \
    && wget -q "$GOLANG_SRC_URL" -O golang.tar.gz \
    && echo "$GOLANG_SRC_SHA256  golang.tar.gz" | sha256sum -c - \
    && tar -C /usr/local -xzf golang.tar.gz \
    && wget -q https://raw.githubusercontent.com/docker-library/golang/master/1.9/alpine3.6/no-pic.patch \
    && cd /usr/local/go/src \
    && patch -p2 -i /go/src/no-pic.patch \
    && ./make.bash \
    && chmod -R 777 /go \

    # Compile golang/dep
    && go get -u github.com/golang/dep/... \
    && cd /go/src/github.com/golang/dep \
    && git checkout ${GODEP_VERSION} \
    && go install github.com/golang/dep/... \
    && mv /go/bin/dep /usr/bin \

    # Clean up
    && apk del --purge -r build-dependencies \
    && rm -rf /usr/local/go /usr/lib/go /go /var/cache/* /var/lib/apk*

ENTRYPOINT ["dep"]
CMD ["-h"]