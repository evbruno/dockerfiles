# Some Dockerfile utils and templates

Using `buildx` for multi-platform images:

```bash
docker buildx create --use
docker buildx inspect --bootstrap
docker buildx build \
  --build-arg OPENJDK=11.0.14 \
  --build-arg SCALA_VER=2.12.12 \
  -t educhaos/scala-openjdk11:2.12.12 \
  -t educhaos/scala-openjdk11:2.12.12_openjdk-11.0.14 \
  -t educhaos/scala-openjdk11:latest \
  --platform linux/amd64,linux/arm64 \
  -f Dockerfile-scala --push .
docker buildx rm
```	
