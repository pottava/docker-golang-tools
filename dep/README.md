Supported tags and respective `Dockerfile` links:  
・latest ([dep/versions/1.8/Dockerfile](https://github.com/pottava/docker-golang-tools/blob/master/dep/versions/1.8/Dockerfile))  
・1.8 ([dep/versions/1.8/Dockerfile](https://github.com/pottava/docker-golang-tools/blob/master/dep/versions/1.8/Dockerfile))  
・1.7 ([dep/versions/1.7/Dockerfile](https://github.com/pottava/docker-golang-tools/blob/master/dep/versions/1.7/Dockerfile))  

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
