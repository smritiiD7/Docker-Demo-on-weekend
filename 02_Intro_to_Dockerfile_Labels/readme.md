
# 🏷️ Docker Labels – Usage and Examples

## 📌 What Are Labels?

Docker **labels** are key-value pairs used to **add metadata** to images, containers, and other Docker objects.  
They help with:

- Organizing and filtering resources
- CI/CD automation
- Integration with orchestration tools (e.g., Kubernetes, Swarm)
- Image authorship and versioning info

---

## ✍️ Add Labels in a Dockerfile

```Dockerfile
FROM nginx
LABEL maintainer="smriti7@example.com"
LABEL version="1.0"
LABEL description="NGINX image serving a static site"
```

Multiple labels in one line:

```Dockerfile
LABEL maintainer="smriti7@example.com" version="2.0" env="prod"
```

---

## 🛠️ Add Labels During Build (CLI)

```bash
docker build -t nginx-image-with-labels:v1 \
  --label "maintainer=smriti7@example.com" \
  --label "env=prod" \
  .
```

---

## ▶️ Add Labels During `docker run`

```bash
docker run -d --label "tier=frontend" nginx-image-with-labels:v1
```

---

## 🔍 Inspect Docker Labels

### Image Labels
```bash
docker inspect nginx-image-with-labels:v1
```

### Format output to show only labels:
```bash
docker image inspect --format='{{ json .Config.Labels }}' nginx-image-with-labels:v1
```

> Output Example:
```json
{
  "maintainer": "smriti7@example.com",
  "env": "prod",
  "version": "1.0"
}
```

### Container Labels
```bash
docker inspect <container-id> | grep Labels -A 5
```

---

## ✅ Use Cases for Labels

| Label Key                    | Purpose                        |
|-----------------------------|--------------------------------|
| `maintainer`                | Author of the image            |
| `version`                   | Version of the image           |
| `env`                       | Deployment environment         |
| `org.opencontainers.*`      | OCI-compliant metadata         |
| `build_id`, `git_commit`    | CI/CD traceability             |

---

## 📌 Best Practices

- Use lowercase keys with hyphens (e.g., `env=prod`)
- Follow [OCI label spec](https://github.com/opencontainers/image-spec/blob/main/annotations.md) if possible
- Avoid placing sensitive information in labels
- Use labels to integrate with monitoring, auditing, and automation

---

## 🧪 Sample: Full Dockerfile with Labels

```Dockerfile
FROM nginx:alpine
LABEL maintainer="smriti7@example.com"
LABEL org.opencontainers.image.title="nginx-static"
LABEL org.opencontainers.image.version="1.0"
LABEL org.opencontainers.image.description="NGINX container with labels"
COPY index.html /usr/share/nginx/html
```

---

Happy Labeling! 🐳
