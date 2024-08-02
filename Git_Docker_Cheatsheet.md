# Cheatsheet -----

## Git Cheatsheet

### Initialization
```bash
git init
```
- Initialize a new Git repository.

### Configuration
```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```
- Set global configuration options.

### Cloning
```bash
git clone <repository_url>
```
- Clone an existing repository.

### Staging Changes
```bash
git add <file_or_directory>
git add .
```
- Stage changes for the next commit.

### Committing
```bash
git commit -m "commit message"
```
- Commit staged changes with a message.

### Viewing Status
```bash
git status
```
- Show the working tree status.

### Viewing History
```bash
git log
```
- Show commit logs.

### Branching
```bash
git branch
git branch <branch_name>
git checkout <branch_name>
git checkout -b <new_branch_name>
```
- List branches, create a branch, switch to a branch, and create/switch to a new branch.

### Merging
```bash
git merge <branch_name>
```
- Merge changes from another branch into the current branch.

### Pushing to Remote
```bash
git remote add origin <remote_repository_url>
git push -u origin <branch_name>
git push
```
- Add a remote repository, push changes to it, and push subsequent changes.

### Pulling from Remote
```bash
git pull
```
- Fetch and integrate changes from the remote repository.

### Stashing Changes
```bash
git stash
git stash pop
```
- Save changes temporarily and retrieve them later.

### Resetting Changes
```bash
git reset --hard <commit_hash>
```
- Reset the working directory to a specific commit.

---

## GitHub/GitLab Cheatsheet

### Actions (GitHub) / Pipelines (GitLab)

#### GitHub Actions
```yaml
name: CI
on: [push, pull_request]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v2
    - name: Set up Node.js
      uses: actions/setup-node@v2
      with:
        node-version: '14'
    - run: npm install
    - run: npm test
```
- Basic GitHub Actions workflow for CI.

#### GitLab CI/CD
```yaml
stages:
  - build
  - test

build_job:
  stage: build
  script:
    - echo "Building the project..."

test_job:
  stage: test
  script:
    - echo "Running tests..."
```
- Basic GitLab CI/CD pipeline example.

### Adding a Repository
```bash
git remote add origin <repository_url>
git push -u origin master
```
- Add a GitHub/GitLab repository and push initial commits.

### Creating Pull/Merge Requests
1. Create a new branch.
2. Push the branch to the remote repository.
3. Navigate to the repository on GitHub/GitLab.
4. Open a Pull Request (GitHub) or Merge Request (GitLab).

### Protecting Branches
- Navigate to repository settings on GitHub/GitLab.
- Add branch protection rules.

---

## Docker Cheatsheet

### Dockerfile
```Dockerfile
# Use an official Python runtime as a parent image
FROM python:3.8-slim-buster

# Set the working directory in the container
WORKDIR /app

# Copy the current directory contents into the container at /app
COPY . /app

# Install any needed packages specified in requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# Make port 80 available to the world outside this container
EXPOSE 80

# Run app.py when the container launches
CMD ["python", "app.py"]
```
- Basic Dockerfile example.

### Docker Compose File
```yaml
version: '3'
services:
  web:
    build: .
    ports:
      - "5000:5000"
  redis:
    image: "redis:alpine"
```
- Basic Docker Compose file example.

## Docker Commands

### Docker Command to Run Images with Port and Volume 

```bash
docker run -d   -p 8080:80 -v /path/on/host:/path/in/container --name my_container my_image
```

### Breakdown of the Command

- `-d`: Run the container in detached mode (in the background).
- `-p 8080:80`: Map port 8080 on the host to port 80 in the container. This means that requests to `localhost:8080` on your host will be forwarded to port 80 in the container.
- `-v /path/on/host:/path/in/container`: Mount a volume from the host to the container. The directory `/path/on/host` on your host machine will be accessible inside the container at `/path/in/container`.
- `--name my_container`: Assign a name (`my_container`) to the container.
- `my_image`: The name of the Docker image to use.

You can adjust the port numbers, volume paths, container name, and image name according to your needs.

#### Build
```bash
docker build -t myapp .
```
- Build an image from a Dockerfile.

#### Run
```bash
docker run -p 4000:80 myapp
```
- Run a container and map ports.

#### List Containers
```bash
docker ps
docker ps -a
```
- List running containers and all containers.

#### Stop/Remove Containers
```bash
docker stop <container_id>
docker rm <container_id>
```
- Stop and remove containers.

#### Images
```bash
docker images
docker rmi <image_id>
```
- List and remove images.

#### Docker Compose
```bash
docker-compose up
docker-compose down
```
- Start and stop services defined in a Docker Compose file.

### Steps to Update and Rebuild Your Docker Image with Docker Compose:

1. **Make Changes to Your Code:**
   Ensure you've saved all your changes to your code.

2. **Use Docker Compose to Rebuild and Restart:**
   Run the following command in the directory containing your `docker-compose.yml` file:
   ```sh
   docker-compose up --build
   ```

   This command tells Docker Compose to:
   - **Rebuild** the images for the services defined in your `docker-compose.yml` file.
   - **Restart** the containers with the updated images.

### Additional Considerations:

- **Remove Orphan Containers:**
  If you have made changes that affect the service definitions (e.g., added or removed services), you might want to remove any orphaned containers:
  ```sh
  docker-compose up --build --remove-orphans
  ```

- **Rebuilding Only Specific Services:**
  If you only want to rebuild specific services, you can specify them:
  ```sh
  docker-compose up --build service_name
  ```

- **Stopping and Removing Containers:**
  If you want to ensure a clean state, you can stop and remove containers before rebuilding:
  ```sh
  docker-compose down
  docker-compose up --build
  ```

### Example Docker Compose Workflow:

1. **Edit your code.**

2. **Rebuild and restart with Docker Compose:**
   ```sh
   docker-compose up --build
   ```
---
