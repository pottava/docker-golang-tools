# Godep v63 (go v1.7)
#
# docker run --rm -v $GOPATH/src:/go/src -w /go/src/github.com/your-account/project pottava/godep:1.7 save ./...
# docker run --rm -v $GOPATH/src:/go/src -w /go/src/github.com/your-account/project pottava/godep:1.7 restore

FROM pottava/golang:1.7

ENV GODEP_VERSION=74

ADD https://github.com/tools/godep/releases/download/v${GODEP_VERSION}/godep_linux_amd64 /go/bin/
RUN chmod +x /go/bin/godep_linux_amd64
ENTRYPOINT ["/go/bin/godep_linux_amd64"]
