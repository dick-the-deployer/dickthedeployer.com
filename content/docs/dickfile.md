+++
date = "2015-11-22T20:11:22+01:00"
title = "Dickfile"
+++

The instructions how to build project should be stored in project repository in a `.dick.yml` file. This design choice 
allows configuration versioning and quick setup at the same time.

The dickfile has two main sections, the `pipeline` and `jobs`.
Pipeline section should contain list of stages with information if certain stage should run automatically.
Jobs section should contain list of jobs, containing list of commands required to complete each job.

```yml
pipeline:
  stages:
  - name: first # name of stage
    autorun: true # if the stage should run automatically
  - name: second
    autorun: true

jobs: 
  - stage: first # name of stage this job belongs to
    name: echo foo # name of this job
    deploy: # list of commands in this job
      - echo foo
    environmentVariables: # list of environment variables injected to each command in this job
      - key: FOO
        value: bar
  - stage: second
    name: echo bar
    deploy:
      - exit 1
```

## Examples

Example `.dick.yml` files are available in [examples](https://github.com/dick-the-deployer/examples) repository. 
Please check different branches for different configuration options.