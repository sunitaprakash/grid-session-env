
# Overview
This action performs the following:

Install python 3.8
Run pip install lightning-grid
Run grid login --username xxx -key xxx

# Usage
Below is . In the production usage, replace main with the current stable build v0.

```
jobs:
  gridai-actions:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: gridai-actions/gridai-login@v0
        with:
          gridai-username: ${{ secrets.GRIDAI_USERNAME }} 
          gridai-key: ${{ secrets.GRIDAI_KEY }}
      - run: |
          grid session pause ${{ secrets.SESSION_NAME }} 
```
## Required
In the repository add the secrets GRIDAI_KEY , GRIDAI_USERNAME & SESSION_NAME 
https://github.com/Azure/actions-workflow-samples/blob/master/assets/create-secrets-for-GitHub-workflows.md


say how one can contribute - this is a great way to get the community to write actions for stopping, deleting, runs etc
