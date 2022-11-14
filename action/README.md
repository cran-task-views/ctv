# Validate CRAN Task View

This GitHub action validates proposed changes to a CRAN task view. It is 
designed for use in the `cran-task-views` GitHub repository, but can be run in
any user repository using the `user` option.

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

name: Validate task view

jobs:
  validate-ctv:
    runs-on: ubuntu-latest
    steps:
      - uses: cran-task-views/ctv/action@main
```

Replace `<TaskViewName>` with the name of the task view. The task view should be
contained in a file named `TaskViewName.md` in the `user/TaskViewName` github 
repository.
