What is RUN in Dockerfile?
RUN is used to execute shell commands during the image build process.

Each RUN instruction:

Executes the command.

Creates a new layer on top of the image.

This layer is saved and reused in later builds (unless cache is disabled).

Example use: installing packages, creating directories, downloading files.

| Feature     | Explanation                                                               |
| ----------- | ------------------------------------------------------------------------- |
| `RUN`       | Executes commands at build time and adds a new image layer                |
| Layers      | Used in later build stages unless cache is disabled                       |
| Cache Issue | Docker may reuse old `RUN` layers                                         |
| Fix         | Use `docker build --no-cache` to force fresh execution                    |
| Example     | `RUN apk --no-cache add curl` installs curl cleanly in Alpine-based image |


📦 Sample RUN Instruction
dockerfile
Copy
Edit
RUN apk --no-cache add curl
Uses apk, the Alpine package manager.

--no-cache ensures no local cache is used inside the image (not related to Docker layer cache, but to apk cache).

curl is being installed in the image.

======