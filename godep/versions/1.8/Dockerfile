# Godep v79 (go v1.8)
#
# docker run --rm -v $GOPATH:/go -w /go/src/github.com/your-account/project pottava/godep save ./...
# docker run --rm -v $GOPATH:/go -w /go/src/github.com/your-account/project pottava/godep update foo/...
# docker run --rm -v $GOPATH:/go -w /go/src/github.com/your-account/project pottava/godep restore

FROM pottava/golang:1.8-builder

ENV GODEP_VERSION=79

RUN apk --no-cache add --virtual build-dependencies git \

    # Compile tools/godep
    && REPOSITORY=$GOPATH/src/github.com/tools/godep \
    && git clone --depth=1 -b v${GODEP_VERSION} https://github.com/tools/godep.git $REPOSITORY \
    && cd $REPOSITORY \
    && go install \

    # Clean up
    && apk del --purge -r build-dependencies \
    && rm -rf /go/src /go/pkg /var/cache/* /var/lib/apk*

ENTRYPOINT ["godep"]
