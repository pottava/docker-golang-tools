# Godep (go v1.6)
#
# docker run --rm -v $GOPATH/src:/go/src -w /go/src/github.com/your-account/project pottava/godep:1.6 save ./...
# docker run --rm -v $GOPATH/src:/go/src -w /go/src/github.com/your-account/project pottava/godep:1.6 restore
#
# docker run --rm -v $GOPATH/src:/go/src -w /go/src/github.com/your-account/project -e GO15VENDOREXPERIMENT=1 pottava/godep:1.6 save ./...
# docker run --rm -v $GOPATH/src:/go/src -w /go/src/github.com/your-account/project -e GO15VENDOREXPERIMENT=1 pottava/godep:1.6 restore

FROM pottava/golang:1.6
RUN go get github.com/tools/godep
ENTRYPOINT ["godep"]
