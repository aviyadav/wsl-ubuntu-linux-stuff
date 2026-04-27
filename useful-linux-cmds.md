# Useful Linux commands

#### Search and delete a file or folder recursivly

```
# forder
find home/codebase/python-base/ -type d -name ".venv" -exec rm -rf {} +

# file
find home/codebase/python-base/ -type d -name ".venv" -delete
```

#### search and list files / folder recursivly

```
find home/codebase/python-base/ -type d -name "data" -exec ls -la {} +
```

