| **Action**               | **Command Syntax**                                                                |
| ------------------------ | --------------------------------------------------------------------------------- |
| **Build Docker image**   | `docker build -t <dockerhub-username>/<image-name>:<tag> <build-context>`         |
| **Run Docker container** | `docker run --name <container-name> -p <host-port>:<container-port> <image-name>` |
| **Tag Docker image**     | `docker tag <source-image>:<tag> <target-image>:<tag>`                            |
| **Login to Docker Hub**  | `docker login`                                                                    |
| **Push Docker image**    | `docker push <dockerhub-username>/<image-name>:<tag>`                             |
| **Pull Docker image**    | `docker pull <dockerhub-username>/<image-name>:<tag>`                             |
| **List images**          | `docker images`                                                                   |
| **List containers**      | `docker ps -a`                                                                    |
| **Stop a container**     | `docker stop <container-name or container-id>`                                    |
| **Remove a container**   | `docker rm <container-name or container-id>`                                      |
| **Remove an image**      | `docker rmi <image-name or image-id>`                                             |
