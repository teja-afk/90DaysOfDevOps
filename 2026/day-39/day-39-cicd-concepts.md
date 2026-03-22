# Day 39 – CI/CD Concepts

## Task 1 – The Problem Without CI/CD

### 1. What can go wrong if 5 developers deploy manually?

- Code conflicts between developers
- One developer may overwrite another's changes
- Bugs may go to production without testing
- Different environments may cause failures
- Deployment mistakes may break the application

Manual deployment is slow, risky, and error-prone.


### 2. What does "It works on my machine" mean?

This means the code runs correctly on the developer’s local system but fails on another system or server.

Reasons:
- Different OS
- Different dependencies
- Different environment variables
- Different versions of software

This is a real problem because production servers are different from developer machines.


### 3. How many times can a team safely deploy manually?

Usually only 1–2 times per day.

Manual deployment takes time and has high risk, so frequent releases are difficult without automation.

CI/CD solves this problem.


--------------------------------------------------

## Task 2 – CI vs CD vs CD

### Continuous Integration (CI)

Continuous Integration is the practice of automatically building and testing code every time a developer pushes changes to the repository.

It helps to:
- Detect bugs early
- Avoid integration conflicts
- Keep the main branch stable

Example:
GitHub Actions runs tests every time code is pushed.


### Continuous Delivery (CD)

Continuous Delivery means the application is automatically built and tested, and is always ready to be deployed, but deployment requires manual approval.

It ensures:
- Code is always in deployable state
- Releases are safe
- Production deployment is controlled

Example:
Pipeline builds Docker image and waits for approval before deploy.


### Continuous Deployment (CD)

Continuous Deployment means every change that passes the pipeline is automatically deployed to production without manual approval.

Used when:
- Tests are very reliable
- Fast release is needed
- DevOps automation is strong

Example:
After tests pass, the app is deployed automatically to server.


--------------------------------------------------

## Task 3 – Pipeline Anatomy

### Trigger
Event that starts the pipeline.

Examples:
- git push
- pull request
- schedule
- manual run


### Stage
A logical phase of pipeline.

Examples:
- build
- test
- deploy


### Job
A job is a group of steps executed on the same runner.


### Step
Single command inside a job.

Example:
- install dependencies
- run tests
- build docker image


### Runner
Machine that executes the pipeline.

Examples:
- GitHub runner
- self-hosted runner
- Jenkins agent


### Artifact
Output produced by a job.

Examples:
- build files
- docker image
- zip package
- logs


--------------------------------------------------

## Task 4 – Pipeline Diagram

Text Diagram:

Developer push → GitHub

        ↓

Trigger Pipeline

        ↓

Stage 1: Build
    - install dependencies
    - compile code

        ↓

Stage 2: Test
    - run unit tests
    - run lint

        ↓

Stage 3: Docker Build
    - build image
    - push to registry

        ↓

Stage 4: Deploy
    - deploy to staging server


--------------------------------------------------

## Task 5 – Explore Open Source Repo

Repository checked: Kubernetes

Folder:
.github/workflows/

Workflow file example:
ci.yml


Trigger:
push / pull_request


Jobs:
Multiple jobs (build, test, lint)


What it does:
- Runs tests
- Checks code formatting
- Builds components
- Validates changes


Observation:
Large projects use many jobs and stages in CI/CD.


--------------------------------------------------

## What I Learned

1. CI/CD automates build, test, and deployment
2. CI finds bugs early before production
3. Pipelines make deployments safe and repeatable
