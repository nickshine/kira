# Simple demo of Docker Multi-Architecture Images

## Build Images
```
docker build -f Dockerfile.arm32v6 -t nshine/kira:arm32v6-latest .
docker build -f Dockerfile.amd64 -t nshine/kira:amd64-latest .

docker push nshine/kira:arm32v6-latest
docker push nshine/kira:amd64-latest
```

## Create the Manifest
```
docker manifest create nshine/kira:latest nshine/kira:amd64-latest nshine/kira:arm32v6-latest

```

## Add Annotations
```
docker manifest annotate nshine/kira:latest nshine/kira:arm32v6-latest --os linux --arch arm
```

## Push Manifest
```
docker manifest push nshine/kira:latest
```
