# Day 32 – Docker Volumes & Networking

## Task
Today's goal is to **solve two real problems: data persistence and container communication**.

Containers are ephemeral — they lose data when removed. And by default, containers can't easily talk to each other. Today you fix both.

---

## Challenge Tasks

### Task 1: The Problem
1. Run a Postgres or MySQL container
![alt text](image.png)
2. Create some data inside it (a table, a few rows — anything)
![alt text](image-1.png)
![alt text](image-2.png)
3. Stop and remove the container
![alt text](image-3.png)
4. Run a new one — is your data still there?
![alt text](image-4.png)
Write what happened and why.
#### Result
- Data was lost.
#### Why?
- Because container filesystem is temporary.
- When container is removed, data inside it is deleted.
---

### Task 2: Named Volumes
1. Create a named volume
![alt text](image-5.png)
2. Run the same database container, but this time **attach the volume** to it
![alt text](image-9.png)
3. Add some data, stop and remove the container
![alt text](image-10.png)
![alt text](image-11.png)
4. Run a brand new container with the **same volume**
![alt text](image-12.png)
5. Is the data still there?
#### Result
- Data still exists

**Verify:** `docker volume ls`, `docker volume inspect`
![alt text](image-14.png)
![alt text](image-13.png)

---

### Task 3: Bind Mounts
1. Create a folder on your host machine with an `index.html` file
2. Run an Nginx container and **bind mount** your folder to the Nginx web directory
![alt text](image-15.png)
3. Access the page in your browser
![alt text](image-16.png)
4. Edit the `index.html` on your host — refresh the browser
![alt text](image-17.png)
Write in your notes: What is the difference between a named volume and a bind mount?
| Feature                 | Named Volume | Bind Mount |
| ----------------------- | ------------ | ---------- |
| Managed by Docker       | Yes          | No         |
| Stored in Docker folder | Yes          | No         |
| Uses host folder        | No           | Yes        |
| Good for DB data        | Yes          | Sometimes  |
| Good for code/dev       | No           | Yes        |

---

### Task 4: Docker Networking Basics
1. List all Docker networks on your machine
![alt text](image-18.png)
2. Inspect the default `bridge` network
![alt text](image-19.png)
3. Run two containers on the default bridge — can they ping each other by **name**?
![alt text](image-20.png)
#### Result: Fails
4. Run two containers on the default bridge — can they ping each other by **IP**?
![alt text](image-21.png)
#### Result: Pass

---

### Task 5: Custom Networks
1. Create a custom bridge network called `my-app-net`
![alt text](image-22.png)
2. Run two containers on `my-app-net`
![alt text](image-23.png)
3. Can they ping each other by **name** now?
![alt text](image-24.png)
4. Write in your notes: Why does custom networking allow name-based communication but the default bridge doesn't?
#### Result:
Works ✅
#### Why?
- Custom bridge network has built-in DNS.
- Default bridge does not support name resolution.
---

### Task 6: Put It Together
1. Create a custom network
![alt text](image-25.png)
2. Run a **database container** (MySQL/Postgres) on that network with a volume for data
![alt text](image-26.png)
3. Run an **app container** (use any image) on the same network
![alt text](image-27.png)
4. Verify the app container can reach the database by container name
![alt text](image-28.png)
---

## Hints
- Volumes: `docker volume create`, `-v volume_name:/path`
- Bind mount: `-v /host/path:/container/path`
- Networking: `docker network create`, `--network`
- Ping: `docker exec container1 ping container2`

---

## Learn in Public
Share what happened when you deleted a container without a volume on LinkedIn. The "aha moment" is real.

`#90DaysOfDevOps` `#DevOpsKaJosh` `#TrainWithShubham`

Happy Learning!
**TrainWithShubham**
