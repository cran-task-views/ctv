# Validate CRAN Task View

This GitHub Action validates proposed changes to a CRAN task view. It is 
designed for use in the `cran-task-views` GitHub organization, but can
be run in any user repository using the `user` option. By default, it will
also run on the 1st of every month to check for deprecated packages.

# Using this workflow

Create a file `user/TaskViewName/.github/workflows/validate-ctv.yml`, 
containing:

```yml
on:
  push:
    branches:
      - main
      - master
    paths:
      - '.github/workflows/validate-ctv.yml'
      - '<TaskViewName>.md'
  pull_request:
    branches:
      - main
      - master
    paths:
      - '.github/workflows/validate-ctv.yml'
      - '<TaskViewName>.md'
  schedule:
    - cron: '30 5 1 * *'

name: Validate task view

jobs:
  validate-ctv:
    runs-on: ubuntu-latest
    steps:
      - uses: cran-task-views/ctv/validate-ctv@main
```

Replace `<TaskViewName>` with the name of the task view. The task view should be
contained in a file named `TaskViewName.md` in the `user/TaskViewName` GitHub 
repository.
