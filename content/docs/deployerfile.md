+++
date = "2015-11-22T20:11:22+01:00"
title = "Deployer File"
+++

The instructions how to build project should be stored in project repository in a `.deployer.yml` file. This design choice
allows configuration versioning and quick setup at the same time.

The deployer file has two main sections, the `pipeline` and `jobs`.
Pipeline section should contain list of stages with information if certain stage should run automatically.
Jobs section should contain list of jobs, containing list of commands required to complete each job.

> Please note that Dick the Deployer Worker runs commands by bash inside docker container. Only containers with bash available will work.

```yml
image: debian:latest

variables: # list of environment variables injected to each command
  - key: VERSION
    value: 1.2.3
    
pipeline:
  stages:
  - name: first # name of stage
    autorun: true # if the stage should run automatically, default false
  - name: second
    autorun: true

jobs: 
  - stage: first # name of stage this job belongs to
    name: echo foo # name of this job
    requireRepository: true # if the job require sources from repository, default false
    deploy: # list of commands in this job
      - echo foo
  - stage: second
    name: echo bar
    deploy:
      - exit 1
```

## Examples

Example `.deployer.yml` files are available in [examples](https://github.com/dick-the-deployer/examples) repository. 
Please check different branches for different configuration options.
