Supported tags and respective `Dockerfile` links:  
・latest ([gox/versions/1.8/Dockerfile](https://github.com/pottava/docker-golang-tools/blob/master/gox/versions/1.8/Dockerfile))  
・go1.8 ([gox/versions/1.8/Dockerfile](https://github.com/pottava/docker-golang-tools/blob/master/gox/versions/1.8/Dockerfile))  
・go1.7 ([gox/versions/1.7/Dockerfile](https://github.com/pottava/docker-golang-tools/blob/master/gox/versions/1.7/Dockerfile))  

# Usage
`docker run --rm -v $GOPATH/src:/go/src -w /go/src/github.com/your-account/project pottava/gox --osarch "linux/amd64" -output "dist/{{.OS}}_{{.Arch}}"`

* with docker-compose.yml

```
build:
  image: pottava/gox
  command: --osarch "linux/amd64" -output "dist/{{.OS}}_{{.Arch}}"
  volumes:
    - $GOPATH/src:/go/src
  working_dir: /go/src/github.com/your-account/project
```
