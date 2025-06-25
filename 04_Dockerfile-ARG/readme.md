🛠️ --build-arg in Docker
✅ What It Is:
--build-arg is a flag you use with docker build to pass build-time variables (defined using ARG in your Dockerfile).

🔹 When to Use It:
To customize the image at build time

To pass version numbers, environment types, or dynamic values to your build

🔧 Build the Image

docker build --build-arg NGINX_VERSION=1.27 -t nginx-image:1.27 .
Here, 1.27 overrides the default 1.26.

| Feature                   | Description                                |
| ------------------------- | ------------------------------------------ |
| Scope                     | Build-time only (not available at runtime) |
| Default value             | Optional in `Dockerfile`                   |
| Override option           | ✅ Use `--build-arg` to override            |
| Visibility in final image | ❌ Not persisted unless passed to `ENV`     |
==============

| Command                              | Effect                                        |
| ------------------------------------ | --------------------------------------------- |
| `docker rm -f $(docker ps -aq)`      | 🚫 Deletes all containers (running + stopped) |
| `docker rmi -f $(docker images -aq)` | 🧯 Deletes all Docker images (forcefully)     |
