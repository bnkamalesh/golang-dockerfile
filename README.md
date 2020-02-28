# Go Dockerfile v0.1.0

[Dockerfiles](https://docs.docker.com/engine/reference/builder/) which can be used to create [Docker image](https://docs.docker.com/engine/docker-overview/#docker-objects) image for your [Go](https://golang.org) app. It makes use of Docker's [multi-stage build feature](https://docs.docker.com/develop/develop-images/multistage-build/) to create the Go application binary, and then attach it to a minimal base image.

There are 3 Dockerfiles provided

1. [Debian](https://www.debian.org/) slim based 
2. [Alpine](https://alpinelinux.org/) based
3. [Scratch](https://hub.docker.com/_/scratch) (no base OS layer)


## How to build the example

```bash
$ docker build -t webgo-helloworld-alpine -f Dockerfile-alpine ./example

$ docker build -t webgo-helloworld-debian -f Dockerfile-debian ./example

$ docker build -t webgo-helloworld-scratch -f Dockerfile-scratch ./example
```

## How to run?

```bash
$ docker run -p 8080:8080 --rm -ti webgo-helloworld-alpine
$ docker run -p 8080:8080 --rm -ti webgo-helloworld-debian
$ docker run -p 8080:8080 --rm -ti webgo-helloworld-scratch
```