Supported tags and respective `Dockerfile` links:  
・latest ([dep/versions/0.3/Dockerfile](https://github.com/pottava/docker-golang-tools/blob/master/dep/versions/0.3/Dockerfile))  
・0.3 ([dep/versions/0.3/Dockerfile](https://github.com/pottava/docker-golang-tools/blob/master/dep/versions/0.3/Dockerfile))  

# Usage

```
docker run --rm -v $GOPATH/src:/go/src -w /go/src/github.com/your-account/project pottava/dep ensure
```

* with docker-compose.yml

```
ensure:
  image: pottava/dep
  command: ensure
  volumes:
    - $GOPATH/src:/go/src
  working_dir: /go/src/github.com/your-account/project
```
