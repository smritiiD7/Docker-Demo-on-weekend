# Ports in Docker

When you run a container, you often want it to communicate with the outside world. Docker gives you **two options** for exposing container ports to your **host machine**:

---

### 🔹 1. **Understanding Port Mapping with `p` Flag**

This is used when you want to **explicitly map a port on your host to a port inside the container**.

### 🔸 How it works:

```jsx
-p host_port:container_port
==============================
host_port: The port on your machine (e.g., your laptop).

container_port: The port inside the container the app is running on.
```

### What it does:

It creates a bridge between your host and container, letting you access the container service directly using your host's IP and port.

### 🔸 Example:

```jsx
docker run --name my-ports-demo1 -p 8090:80 -d demo14-docker-singleport:v1

```

- This maps **host port 8090** → **container port 80**
- So if your container serves a website on port 80, you can open `http://localhost:8090` in your browser and access it.

### 🔹 2. **Publishing All Exposed Ports with `P` Flag**

This is used when you want Docker to **automatically assign random high-numbered ports on the host** to all **EXPOSED** ports in your container.

### 🔸 How it works:

```jsx
-P
```

### 🔸 What it does:

- Useful when your container has **multiple ports exposed**, and you **don’t want to manually map** each one.
- Docker will **dynamically assign** a random host port to each container port.
- You can check what ports got mapped by running:

docker ps
docker run --name my-ports-demo3 -P -d demo14-docker-multiport:v1