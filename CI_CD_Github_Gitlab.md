### GitHub Actions CI/CD

GitHub Actions is a powerful, flexible CI/CD tool integrated into GitHub repositories. Workflows are defined using YAML files placed in the `.github/workflows` directory of your repository.

#### Example Workflow

**.github/workflows/ci.yml**

```yaml
name: CI Pipeline

on:
  push:
    branches:
      - main
  pull_request:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest
    
    steps:
    - name: Checkout Code
      uses: actions/checkout@v2

    - name: Set up Python
      uses: actions/setup-python@v2
      with:
        python-version: '3.9'

    - name: Install Dependencies
      run: |
        python -m pip install --upgrade pip
        pip install -r requirements.txt

    - name: Run Tests
      run: |
        pytest
```

### GitLab CI/CD

GitLab CI/CD is another robust CI/CD tool integrated into GitLab repositories. It uses `.gitlab-ci.yml` file at the root of the repository.

#### Example Workflow

**.gitlab-ci.yml**

```yaml
stages:
  - build
  - test

variables:
  PYTHON_VERSION: "3.9"

before_script:
  - apt-get update
  - apt-get install -y python3-pip

build:
  stage: build
  script:
    - pip3 install -r requirements.txt

test:
  stage: test
  script:
    - pytest
```

### Key Concepts and Best Practices

#### Triggers

- **GitHub Actions**: Use `on` to specify events like `push`, `pull_request`, and more.
- **GitLab CI/CD**: Use `only` or `except` to specify conditions for running jobs.

#### Secrets and Credentials

- **GitHub Actions**: Store secrets in the repository settings under "Secrets and variables".
  ```yaml
  env:
    MY_SECRET: ${{ secrets.MY_SECRET }}
  ```

- **GitLab CI/CD**: Store secrets in GitLab's CI/CD settings under "Variables".
  ```yaml
  variables:
    MY_SECRET: $MY_SECRET
  ```

#### YAML File Best Practices

1. **Modularity**: Break down complex workflows into multiple jobs and steps.
2. **Reusability**: Use reusable workflows or templates.
3. **Security**: Use secrets and avoid hardcoding sensitive information.
4. **Optimization**: Cache dependencies to speed up builds.
5. **Documentation**: Comment your YAML files for clarity.

### Example: Advanced GitHub Actions Workflow

**.github/workflows/advanced-ci.yml**

```yaml
name: Advanced CI Pipeline

on:
  push:
    branches: [main, develop]
  pull_request:
    branches: [main, develop]

jobs:
  setup:
    runs-on: ubuntu-latest
    steps:
    - name: Checkout Code
      uses: actions/checkout@v2

    - name: Set up Python
      uses: actions/setup-python@v2
      with:
        python-version: '3.9'

  install-dependencies:
    needs: setup
    runs-on: ubuntu-latest
    steps:
    - name: Install Dependencies
      run: |
        python -m pip install --upgrade pip
        pip install -r requirements.txt

  run-tests:
    needs: install-dependencies
    runs-on: ubuntu-latest
    steps:
    - name: Run Tests
      run: |
        pytest

  deploy:
    needs: run-tests
    runs-on: ubuntu-latest
    if: github.ref == 'refs/heads/main' && github.event_name == 'push'
    steps:
    - name: Deploy to Production
      run: |
        echo "Deploying to production..."
        # Add deployment script/commands here
```

### Example: Advanced GitLab CI/CD Workflow

**.gitlab-ci.yml**

```yaml
stages:
  - setup
  - build
  - test
  - deploy

variables:
  PYTHON_VERSION: "3.9"

before_script:
  - apt-get update
  - apt-get install -y python3-pip

setup:
  stage: setup
  script:
    - pip3 install --upgrade pip

build:
  stage: build
  script:
    - pip3 install -r requirements.txt

test:
  stage: test
  script:
    - pytest

deploy:
  stage: deploy
  only:
    - main
  script:
    - echo "Deploying to production..."
    # Add deployment script/commands here
```

### Advanced Workflow

```yaml
name: Advanced CI Pipeline

on:
  push:
    branches: [main, develop]
  pull_request:
    branches: [main, develop]

jobs:
  setup:
    runs-on: ubuntu-latest
    steps:
    - name: Checkout Code
      uses: actions/checkout@v2

    - name: Set up Python
      uses: actions/setup-python@v2
      with:
        python-version: '3.9'

  install-dependencies:
    needs: setup
    runs-on: ubuntu-latest
    steps:
    - name: Install Dependencies
      run: |
        python -m pip install --upgrade pip
        pip install -r requirements.txt

  run-tests:
    needs: install-dependencies
    runs-on: ubuntu-latest
    steps:
    - name: Run Tests
      run: |
        pytest

  deploy:
    needs: run-tests
    runs-on: ubuntu-latest
    if: github.ref == 'refs/heads/main' && github.event_name == 'push'
    steps:
    - name: Deploy to Production
      run: |
        echo "Deploying to production..."
        # Add deployment script/commands here
```

## GitLab CI/CD

### Basic Workflow

```yaml
stages:
  - build
  - test

variables:
  PYTHON_VERSION: "3.9"

before_script:
  - apt-get update
  - apt-get install -y python3-pip

build:
  stage: build
  script:
    - pip3 install -r requirements.txt

test:
  stage: test
  script:
    - pytest
```

### Advanced Workflow

```yaml
stages:
  - setup
  - build
  - test
  - deploy

variables:
  PYTHON_VERSION: "3.9"

before_script:
  - apt-get update
  - apt-get install -y python3-pip

setup:
  stage: setup
  script:
    - pip3 install --upgrade pip

build:
  stage: build
  script:
    - pip3 install -r requirements.txt

test:
  stage: test
  script:
    - pytest

deploy:
  stage: deploy
  only:
    - main
  script:
    - echo "Deploying to production..."
    # Add deployment script/commands here
```

### Best Practices

1. **Modularity**: Break down complex workflows into multiple jobs and steps.
2. **Reusability**: Use reusable workflows or templates.
3. **Security**: Use secrets and avoid hardcoding sensitive information.
4. **Optimization**: Cache dependencies to speed up builds.
5. **Documentation**: Comment your YAML files for clarity.

### Secrets and Credentials

#### GitHub Actions

Store secrets in the repository settings under "Secrets and variables".

```yaml
env:
  MY_SECRET: ${{ secrets.MY_SECRET }}
```

#### GitLab CI/CD

Store secrets in GitLab's CI/CD settings under "Variables".

```yaml
variables:
  MY_SECRET: $MY_SECRET
```
