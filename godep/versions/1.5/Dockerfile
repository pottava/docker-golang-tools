# Godep v57 (go v1.5)
#
# docker run --rm -v $GOPATH/src:/go/src -w /go/src/github.com/your-account/project pottava/godep:1.5 save ./...
# docker run --rm -v $GOPATH/src:/go/src -w /go/src/github.com/your-account/project pottava/godep:1.5 restore
#
# docker run --rm -v $GOPATH/src:/go/src -w /go/src/github.com/your-account/project -e GO15VENDOREXPERIMENT=1 pottava/godep:1.5 save ./...
# docker run --rm -v $GOPATH/src:/go/src -w /go/src/github.com/your-account/project -e GO15VENDOREXPERIMENT=1 pottava/godep:1.5 restore

FROM pottava/golang:1.5

ENV GODEP_VERSION=63

ADD https://github.com/tools/godep/releases/download/v${GODEP_VERSION}/godep_linux_amd64 /go/bin/
RUN chmod +x /go/bin/godep_linux_amd64
ENTRYPOINT ["/go/bin/godep_linux_amd64"]
