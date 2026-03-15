# Day 31 – Dockerfile: Build Your Own Images

## Task
Today's goal is to **write Dockerfiles and build custom images**.

This is the skill that separates someone who uses Docker from someone who actually ships with Docker.

---

## Challenge Tasks

### Task 1: Your First Dockerfile
1. Create a folder called `my-first-image`
2. Inside it, create a `Dockerfile` that:
   - Uses `ubuntu` as the base image
   - Installs `curl`
   - Sets a default command to print `"Hello from my custom image!"`
3. Build the image and tag it `my-ubuntu:v1`
![alt text](image.png)
4. Run a container from your image
![alt text](image-1.png)

**Verify:** The message prints on `docker run`

---

### Task 2: Dockerfile Instructions
Create a new Dockerfile that uses **all** of these instructions:
- `FROM` — base image
- `RUN` — execute commands during build
- `COPY` — copy files from host to image
- `WORKDIR` — set working directory
- `EXPOSE` — document the port
- `CMD` — default command
![alt text](image-3.png)
Build and run it. Understand what each line does.
![alt text](image-4.png)
![alt text](image-5.png)

---

### Task 3: CMD vs ENTRYPOINT
1. Create an image with `CMD ["echo", "hello"]` — run it,
![alt text](image-6.png)
then run it with a custom command.
![alt text](image-7.png)
![alt text](image-8.png)
 What happens?
👉 CMD can be overridden

2. Create an image with `ENTRYPOINT ["echo"]` — run it,
![alt text](image-10.png)
then run it with additional arguments.
![alt text](image-11.png)
What happens?
👉 ENTRYPOINT always runs

3. Write in your notes: When would you use CMD vs ENTRYPOINT?
| Feature          | CMD       | ENTRYPOINT |
| ---------------- | --------- | ---------- |
| Can override     | Yes       | No         |
| Default command  | Yes       | Yes        |
| Used for apps    | Sometimes | Yes        |
| Used for scripts | Rare      | Yes        |

---

### Task 4: Build a Simple Web App Image
1. Create a small static HTML file (`index.html`) with any content
2. Write a Dockerfile that:
   - Uses `nginx:alpine` as base
   - Copies your `index.html` to the Nginx web directory
![alt text](image-12.png)
3. Build and tag it `my-website:v1`
![alt text](image-15.png)
4. Run it with port mapping and access it in your browser
![alt text](image-14.png)
![alt text](image-13.png)
---

### Task 5: .dockerignore
1. Create a `.dockerignore` file in one of your project folders
2. Add entries for: `node_modules`, `.git`, `*.md`, `.env`
![alt text](image-16.png)
3. Build the image — verify that ignored files are not included
##### Why?
Prevents unnecessary files from being copied into image

Benefits
- Faster build
- Smaller image
- Better security
---

### Task 6: Build Optimization
1. Build an image, then change one line and rebuild — notice how Docker uses **cache**
2. Reorder your Dockerfile so that frequently changing lines come **last**
3. Write in your notes: Why does layer order matter for build speed?

### Test caching
#### Build
```
docker build -t cache-test:v1 .
```
Change one line
#### Build again
```
docker build -t cache-test:v2 .
```
Docker reused previous layers

Optimized Dockerfile Example
#### Bad
```
COPY . .
RUN npm install
```
#### Good
```
COPY package.json .
RUN npm install
COPY . .
```
Why layer order matters
Docker caches layers.
If early layer changes → all next layers rebuild

So:
#### Put changing lines last
#### Put stable lines first

#### Benefits:
- Faster builds
- Less network usage
- Efficient CI/CD
---

## Hints
- Build: `docker build -t name:tag .`
- The `.` at the end is the build context
- `COPY . .` copies everything from host to container
- Nginx serves files from `/usr/share/nginx/html/`

---


## Learn in Public
Share your custom Docker image or Nginx screenshot on LinkedIn.

`#90DaysOfDevOps` `#DevOpsKaJosh` `#TrainWithShubham`

Happy Learning!
**TrainWithShubham**
