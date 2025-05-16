# Validate CRAN Task View

This GitHub Action validates proposed changes to a CRAN task view. It is 
designed for use in the `cran-task-views` GitHub organization, but can
be run in any user repository using the `user` option.

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

# Scheduling workflows

By default, the above `.yml` will trigger the workflow to check for archived packages
at [5:30 am on the 1st of every month](https://crontab.guru/#30_5_1_*_*).
If you would not like to trigger monthly workflows, you can modify the `cron` value
or remove the `schedule` component entirely. See more details [here](https://docs.github.com/en/actions/writing-workflows/choosing-when-your-workflow-runs/events-that-trigger-workflows#schedule).
