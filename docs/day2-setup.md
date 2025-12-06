# Day 2  Creating a Dockerfile
---

## What I did
- Created a simple node api that outputs hello world
- Set up a dockerfile
- successfully ran the docker file

## What I learnt:
- docker commands and how to use them
- Implemented concept of Containers
- Building and running the docker file


## Next Steps
- learn how to share data among containers
- deploy a simple python add code using docker  

---


## Commands:

### 1. FROM

```dockerfile
FROM <image>
````

- **Purpose:** Set the base image for the container.
- **Notes:** Every container starts from a base image (e.g., `node:24`).


### 2. WORKDIR

```dockerfile
WORKDIR <directory>
```

- **Purpose:** Set the working directory inside the container.
- **Notes:** All subsequent commands are executed relative to this directory.


### 3. COPY

```dockerfile
COPY <source> <destination>
```

- **Purpose:** Copy files/folders from host to container.
- **Notes:**
    - Often used for `package.json` first to leverage caching.
    - Can copy all files: `COPY . .`


### 4. RUN

```dockerfile
RUN <command>
```

- **Purpose:** Execute commands in the container during build.
- **Notes:**
    - Used to install dependencies, build the app, etc.
    - Each `RUN` instruction creates a new layer.


### 5. ENV

```dockerfile
ENV <key>=<value>
```

- **Purpose:** Set environment variables inside the container.
- **Notes:**
    - Example: `ENV PORT=8080`
    - Accessible in Node via `process.env.<key>`.


### 6. EXPOSE

```dockerfile
EXPOSE <port>
```

- **Purpose:** Document which port the container listens on.
- **Notes:**
    - Does **not** actually publish the port; use `docker run -p` for that.


### 7. CMD

```dockerfile
CMD ["executable", "param1", "param2"]
```

- **Purpose:** Define the default command to run when the container starts.
- **Notes:**
    - Only one `CMD` per Dockerfile.
    - Exec form (array syntax) avoids using a shell.
    - Example: `CMD ["node", "src/index.js"]`

---

## .dockerignore

```
<file/folder>
```

- **Purpose:** Prevent files from being copied into the Docker image.
- **Notes:**
    - Useful for ignoring `node_modules`, logs, or other local files.

---

## Docker Layers & Caching

- Every instruction creates a new layer.
- Docker caches layers if nothing has changed.
- Proper ordering (dependencies before code) optimizes build speed.