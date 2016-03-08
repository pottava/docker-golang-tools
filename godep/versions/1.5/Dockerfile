# Godep v57 (go v1.5)
#
# docker run --rm -v $GOPATH/src:/go/src -w /go/src/github.com/your-account/project pottava/godep:1.5 save ./...
# docker run --rm -v $GOPATH/src:/go/src -w /go/src/github.com/your-account/project pottava/godep:1.5 restore
#
# docker run --rm -v $GOPATH/src:/go/src -w /go/src/github.com/your-account/project -e GO15VENDOREXPERIMENT=1 pottava/godep:1.5 save ./...
# docker run --rm -v $GOPATH/src:/go/src -w /go/src/github.com/your-account/project -e GO15VENDOREXPERIMENT=1 pottava/godep:1.5 restore

FROM pottava/golang:1.5

RUN go get github.com/tools/godep \
      && rm -rf /go/pkg /go/src

ENTRYPOINT ["godep"]
