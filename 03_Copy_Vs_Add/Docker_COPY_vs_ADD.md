
# 📦 COPY vs ADD in Dockerfile

In a `Dockerfile`, both `COPY` and `ADD` are used to transfer files into the image. However, they serve slightly different purposes.

---

## 🔍 Key Differences

| Feature                  | `COPY`                                            | `ADD`                                                                   |
|--------------------------|--------------------------------------------------|-------------------------------------------------------------------------|
| **Purpose**              | Only copies files/directories                    | Copies files **and** has extra features                                 |
| **Use Case**             | When you just need to copy files                 | When you need archive extraction or URL fetching                        |
| **Supports Remote URLs** | ❌ No                                             | ✅ Yes (for HTTP/HTTPS only)                                            |
| **Handles Archives**     | ❌ No                                             | ✅ Yes (`.tar`, `.tar.gz`, etc. are auto-extracted)                     |
| **Syntax**               | `COPY <src> <dest>`                              | `ADD <src> <dest>`                                                      |
| **Best Practice**        | Use by default                                   | Use **only** when `ADD`'s features are specifically needed              |

---

## ✅ Examples

### COPY – Recommended for Simplicity

```Dockerfile
COPY ./app /usr/src/app
COPY requirements.txt /app/
```

### ADD – For Archives and URLs

```Dockerfile
# Extract tar.gz file automatically
ADD static-site.tar.gz /usr/share/nginx/html/

# Download file from URL (not recommended for complex cases)
ADD https://example.com/config.yaml /etc/myapp/config.yaml
```

---

## 📌 Best Practices

- Use `COPY` by default for predictable behavior.
- Only use `ADD` for:
  - Auto-extracting `.tar` archives
  - Downloading a file directly from a remote URL (prefer `curl` or `wget` instead).

---

## 🧠 TL;DR

| Use Case                | Instruction |
|-------------------------|-------------|
| Just copying files      | ✅ Use `COPY` |
| Need auto-extraction    | ✅ Use `ADD`  |
| Need to pull from URL   | ⚠️ Use `ADD`, or better: `RUN curl -O <url>` |

---

Happy Dockering! 🐳
