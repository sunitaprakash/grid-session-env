Pause a session using a cron job

# Overview
This action performs the following:
- Install python 3.8
- Run pip install lightning-grid
- Run grid login --username xxx -key xxx
- Pauses a session based on what you define as GitHub's SESSION_NAME secret

# Usage
To pause a session in cron fashion. Below is scheduled-SessionPause.yml. 

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
This Github repository can be used to start, resume or delete a session. 
- grid session create ${{ secrets.SESSION_NAME }} 
- grid session resume ${{ secrets.SESSION_NAME }} 
- grid session delete ${{ secrets.SESSION_NAME }} 

## Required
The repository requires the below secrets. See the offical [documentation](https://github.com/Azure/actions-workflow-samples/blob/master/assets/create-secrets-for-GitHub-workflows.md) for a walkthrough on creating secrets for GitHub workflows.
- GRIDAI_KEY 
- GRIDAI_USERNAME 
- SESSION_NAME 





