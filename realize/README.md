Supported tags and respective `Dockerfile` links:  
・latest ([realize/versions/1.3/Dockerfile](https://github.com/pottava/docker-golang-tools/blob/master/realize/versions/1.3/Dockerfile))  
・1.3 ([realize/versions/1.3/Dockerfile](https://github.com/pottava/docker-golang-tools/blob/master/realize/versions/1.3/Dockerfile))  
・1.2 ([realize/versions/1.2/Dockerfile](https://github.com/pottava/docker-golang-tools/blob/master/realize/versions/1.2/Dockerfile))  

# Usage

```
docker run --rm -v $GOPATH/src:/go/src -w /go/src/github.com/your-account/project pottava/realize add
docker run --rm -v $GOPATH/src:/go/src -w /go/src/github.com/your-account/project pottava/realize run
```

* with docker-compose.yml

```
ensure:
  image: pottava/realize
  command: add
  volumes:
    - $GOPATH/src:/go/src
  working_dir: /go/src/github.com/your-account/project
```
