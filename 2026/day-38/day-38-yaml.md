# Day 38 - YAML Basics

## person.yaml

```yaml
name: Teja Poosa
role: DevOps Learner
experience_years: 0
learning: true

tools:
  - linux
  - git
  - github
  - github-actions
  - kubernetes
  - docker

hobbies: [coding, gaming, music]
```

## server.yaml

```yaml
server:
  name: prod-server
  ip: 192.168.1.10
  port: 8080

database:
  host: localhost
  name: app_db
  credentials:
    user: admin
    password: secret123

startup_script_pipe: |
  echo "Starting server"
  docker compose up -d
  echo "Done"

startup_script_fold: >
  echo "Starting server"
  docker compose up -d
  echo "Done"
```

## What I learned

1. YAML uses spaces only, never tabs
2. Lists can be written using dash format or inline format
3. | keeps new lines, > folds text into one line
