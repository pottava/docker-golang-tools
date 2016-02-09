# Godep (go v1.5)
#
# docker run --rm -v $GOPATH/src:/go/src -w /go/src/github.com/your-account/project pottava/godep save ./...
# docker run --rm -v $GOPATH/src:/go/src -w /go/src/github.com/your-account/project pottava/godep restore
#
# docker run --rm -v $GOPATH/src:/go/src -w /go/src/github.com/your-account/project -e GO15VENDOREXPERIMENT=1 pottava/godep save ./...
# docker run --rm -v $GOPATH/src:/go/src -w /go/src/github.com/your-account/project -e GO15VENDOREXPERIMENT=1 pottava/godep restore

FROM pottava/golang:1.5
RUN go get github.com/tools/godep
ENTRYPOINT ["godep"]
