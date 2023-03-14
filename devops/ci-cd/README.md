# CI/CD (Continuous Integration & Continuous Deployment)

Automating testing, building, and deployment pipelines.

## GitHub Actions Workflow Example
A configuration file located under `.github/workflows/ci.yml` in your repository.

```yaml
name: Django CI

on:
  push:
    branches: [ main, develop ]
  pull_request:
    branches: [ main ]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3

    - name: Set up Python
      uses: actions/setup-python@v4
      with:
        python-version: '3.11'

    - name: Install Dependencies
      run: |
        python -m pip install --upgrade pip
        pip install -r requirements.txt

    - name: Run Tests
      run: |
        python manage.py test
```

## CD Deployment Strategies
*   **Blue-Green Deployment:** Maintaining two identical environments (Blue and Green). Only one serves live traffic. You deploy new releases to Green, run tests, then switch router traffic to Green.
*   **Canary Deployment:** Rolling out a release gradually to a small subset of users (e.g., 5%) before deploying system-wide.
*   **Rolling Update:** Sequentially replacing instances of the old version with instances of the new version to prevent downtime.
