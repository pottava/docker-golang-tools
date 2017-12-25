# golang/dep v0.3
#
# docker run --rm pottava/dep:0.3 --help
# docker run --rm -v $GOPATH/src:/go/src -w /go/src/github.com/your-account/project pottava/dep:0.3 ensure

FROM alpine:3.7

ENV GODEP_VERSION=v0.3.2 \
    GOPATH=/go \
    PATH=/go/bin:/usr/local/go/bin:$PATH

WORKDIR /go/src

RUN apk --no-cache add git
RUN apk --no-cache add --virtual build-dependencies bash gcc musl-dev openssl go \

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
