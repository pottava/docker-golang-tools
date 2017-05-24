Supported tags and respective `Dockerfile` links:  
・latest ([dep/versions/1.8/Dockerfile](https://github.com/pottava/docker-golang-tools/blob/master/dep/versions/1.8/Dockerfile))  

# Usage

`docker run --rm -v $GOPATH/src:/go/src -w /go/src/github.com/your-account/project pottava/godep save ./...`  
`docker run --rm -v $GOPATH/src:/go/src -w /go/src/github.com/your-account/project pottava/godep restore`

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
  command: update foo/...
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
