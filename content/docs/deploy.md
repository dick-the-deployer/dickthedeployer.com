+++
date = "2015-11-22T20:11:22+01:00"
title = "Deployment"
+++

There is an automated deployment for quick installation. You can set various options that should take care of most configurations. 
However, if you want a full customized install, you can treat the automated deployment script as an example.

Automated deployment will deploy Dick the Deployer using current Docker host. 

> Note: you must have a Docker available.

Once deployed, the script will output the URL to connect and command required to run some workers.

```bash
curl https://dickthedeployer.com/deploy | bash -s
```


For full usage details:
```bash
curl -s https://dickthedeployer.com/deploy | bash -s -- -h
```

```bash
  ACTION: this is the action to use (deploy-web, upgrade-web, remove-web, deploy-workers, upgrade-workers, remove-workers)
  VERSION: version of docker images to use, default latest
  PORT: port to run web, default 8080
  WORKERS: this is the number of workers to create in deploy-workers action
  PREFIX: this is the prefix used by all Dick The Deployer components
  DICK_WEB_ADDRESS: this is the Dick The Deployer Web addres used by workers to register in
```

> Note: all variables are optional.

There are also several advanced options not included in full usage, please refer to the script content for details.

## Options

To customize the deployment, you can specify the following environment variables.

### Action

This controls the action for the script. Available options are:

* `deploy-web`: Deploy new Dick the Deployer instance
* `upgrade-web`: Upgrade Dick the Deployer instance.
* `remove-web`: Remove Dick the Deployer instance. (Some additional steps may be require, as printed by script)
* `deploy-workers`: Deploy two Workers and links them to Web. `DICK_WEB_ADDRESS` is required.
* `upgrade-workers`: Upgrade each available Worker instance.
* `remove-workers`: Remove each Worker instance.

### Version

Version of Dick the Deployer container's pulled from registry.

### PORT

Port used by Dick the Deployer - Web module. 
