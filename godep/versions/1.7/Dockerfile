# Godep v63 (go v1.7)
#
# docker run --rm -v $GOPATH/src:/go/src -w /go/src/github.com/your-account/project pottava/godep:1.7 save ./...
# docker run --rm -v $GOPATH/src:/go/src -w /go/src/github.com/your-account/project pottava/godep:1.7 restore

FROM pottava/golang:1.7

ENV GODEP_VERSION=75

RUN mkdir -p $GOPATH/src/github.com/tools/ \
    && cd $GOPATH/src/github.com/tools/ \
    && git clone --depth=1 -b v${GODEP_VERSION} https://github.com/tools/godep.git \
    && cd godep \
    && go install \
    && rm -rf /go/src /go/pkg

ENTRYPOINT ["godep"]
