# Godep v55 (go v1.4)
#
# docker run --rm -v $GOPATH/src:/go/src -w /go/src/github.com/your-account/project pottava/godep:1.4 save ./...
# docker run --rm -v $GOPATH/src:/go/src -w /go/src/github.com/your-account/project pottava/godep:1.4 restore

FROM pottava/golang:1.4

RUN go get github.com/tools/godep \
      && rm -rf /go/pkg /go/src

ENTRYPOINT ["godep"]
