+++
date = "2015-11-22T20:11:22+01:00"
title = "Dick the Deployer Walkthrough"
+++

This is an overview of Dick the Deployer.

## Abstract

Dick the Deployer organizes work in projects. Each project is based on certain repository and ref (for example `master`).
The repository should contain `.deployer.yml` file with the pipeline definition. You can read more about this file in 
[deployer file](/docs/deployerfile) section.

## Projects

The projects section provides a single view of all projects in the Dick the Deployer.
You can see what is the current status of each pipeline, when the build was started, 
the last commit message and more. There are also several buttons allowing you to start 
pipeline manually, start selected stage or restart stage build.

![Projects](/images/dashboard1.png)

## Builds

The builds section provides history of pipelines for selected project. You can start (or restart) 
any stage build of any pipeline run. There is also information about commit message, build number 
and time when the build was started.

![Projects](/images/builds1.png)

## Build

The build section provides summary for certain build. You can monitor build progress of every job in selected stage, 
including build output in near real time.

![Projects](/images/output1.png)


## Settings

The setting section provides several options for project management. You can edit ref, repository and environment variables.
Using this section you can also rename, move or delete project.

![Projects](/images/settings1.png)

## Groups

The groups section presents groups available in Dick the Deployer.

![Projects](/images/groups1.png)

