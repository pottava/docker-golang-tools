# Gox (go v1.11)
#
# docker run --rm -v $GOPATH/src:/go/src -w /go/src/github.com/your-account/project pottava/gox:go1.11 --osarch "linux/amd64" -output "dist/{{.OS}}_{{.Arch}}"

FROM pottava/golang:1.11-builder

RUN apk --no-cache add --virtual build-dependencies git \
    && go get -u github.com/mitchellh/gox \
    && apk del --purge -r build-dependencies \
    && rm -rf /go/src/*

RUN apk --no-cache add gcc musl-dev

ENTRYPOINT ["gox"]
CMD ["-h"]
