<p align="center"><img src="https://user-images.githubusercontent.com/1092882/86526373-07f1d700-beb1-11ea-815b-934d2ea67e0a.png" alt="docker gopher" width="256px"/></p>

# Go Dockerfile v0.1.2

[Dockerfiles](https://docs.docker.com/engine/reference/builder/) to build [Docker images](https://docs.docker.com/engine/docker-overview/#docker-objects) for your [Go](https://golang.org) app. It makes use of Docker's [multi-stage build feature](https://docs.docker.com/develop/develop-images/multistage-build/) to create the Go application binary, and then attach it to a minimal base image. The Go version used is `1.14`, though it should work for most Go versions (not tested). You'll have to tweak the Dockerfile to `COPY` any static files required by the application, to be copied to the final image.

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

## The gopher

The gopher used here was created using [Gopherize.me](https://gopherize.me/). The expert Docker gopher tells us how to build production ready, secure, Docker images for Go applications! 