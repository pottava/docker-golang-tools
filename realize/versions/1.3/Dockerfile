# realize v1.3
#
# docker run --rm -v $GOPATH/src:/go/src -w /go/src/github.com/your-account/project pottava/realize:1.3 run

FROM pottava/golang:1.8

ENV REALIZE_VERSION=1.3

RUN apk --no-cache add --virtual build-dependencies git \
    && git config --global http.https://gopkg.in.followRedirects true \

    # Compile realize
    && go get github.com/tockins/realize \
    && cd /go/src/github.com/tockins/realize \
    && git checkout v${REALIZE_VERSION} \
    && go install github.com/tockins/realize \

    # Clean up
    && apk del --purge -r build-dependencies \
    && rm -rf /go/src/*

RUN apk --no-cache add gcc musl-dev

ENTRYPOINT ["realize"]
CMD ["-h"]
