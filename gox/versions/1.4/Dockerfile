# Gox (go v1.4)
#
# This image works only if OS arch is `linux/amd64`..
# docker run --rm -v $GOPATH/src:/go/src -w /go/src/github.com/your-account/project pottava/gox:1.4 --osarch "linux/amd64" -output "dist/{{.OS}}_{{.Arch}}"

FROM golang:1.4-alpine

RUN apk --no-cache add --virtual build-dependencies git \
      && go get -u github.com/mitchellh/gox \
      && apk del --purge build-dependencies \
      && rm -rf /go/pkg /go/src

ENTRYPOINT ["/go/bin/gox"]
CMD ["-h"]
