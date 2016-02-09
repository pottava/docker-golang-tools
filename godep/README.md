Supported tags and respective `Dockerfile` links:
・latest ([godep/versions/1.5/Dockerfile](https://github.com/pottava/docker-golang-tools/blob/master/godep/versions/1.5/Dockerfile))
・go1.5 ([godep/versions/1.5/Dockerfile](https://github.com/pottava/docker-golang-tools/blob/master/godep/versions/1.5/Dockerfile))

# Usage
`docker run --rm -v $GOPATH/src:/go/src -w /go/src/github.com/your-account/project pottava/godep save ./...`
`docker run --rm -v $GOPATH/src:/go/src -w /go/src/github.com/your-account/project pottava/godep restore`

* with GO15VENDOREXPERIMENT:

`docker run --rm -v $GOPATH/src:/go/src -w /go/src/github.com/your-account/project -e GO15VENDOREXPERIMENT=1 pottava/godep save ./...`
`docker run --rm -v $GOPATH/src:/go/src -w /go/src/github.com/your-account/project -e GO15VENDOREXPERIMENT=1 pottava/godep restore`

* with docker-compose.yml

```
save:
  image: pottava/godep
  command: save ./...
  volumes:
    - $GOPATH/src:/go/src
  working_dir: /go/src/github.com/your-account/project

update:
  image: pottava/godep
  command: update github.com/...
  volumes:
    - $GOPATH/src:/go/src
  working_dir: /go/src/github.com/your-account/project

restore:
  image: pottava/godep
  command: restore
  volumes:
    - $GOPATH/src:/go/src
  working_dir: /go/src/github.com/your-account/project
```
