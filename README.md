# httpbin-arm64

## HTTP Request & Response Service

See http://httpbin.org for more information.

## Build ARM64 Image

Based on `ubuntu:18.04` arm64

Steps to be followed:

- Clone the original Github repo https://github.com/postmanlabs/httpbin
- Replace the original Dockerfile with [Dockerfile](./Dockerfile)
- copy [version.rc](./version.rc) to the repo directory
- build the image and push it wherever you want

```shell
source ./version.rc

docker rmi httpbin-arm64:local

docker build -t httpbin-arm64:local --build-arg UB_VER=${UB_VER} --build-arg UB_SHA=${UB_SHA} .

docker tag httpbin-arm64:local your-repo/httpbin:arm64

docker push your-repo/httpbin:arm64
```
