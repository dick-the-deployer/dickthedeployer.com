+++
date = "2015-11-22T20:11:22+01:00"
title = "Parametrization"
+++

Dick the Deployer enables parametrization of build scripts using environment variables. 
Values that should remain secret can be provided using Dick Web by selecting `secure` option. 
Those variables will not be visible in build output. 

## Providing Environment Variables

There are three ways of providing environment variables:

* manually when starting pipeline with options,
* by `variables` section in `.deployer.yml` configuration file,
* and finally by project options in Dick Web.

## Environment Variables Order

There are several ways of providing environment variables to the job. Variables can be injected
by setting them to configuration on Dick the Deployer Web, can be provided via `yml` file and 
by setting them when triggering the job manually with options.

Each conflict in variable names is resolved with priorities in descending order as follows:

* most important are variables set manually (or via build hook),
* then variables defined in `yml` file,
* finally variables configured in project on Dick Web have lowest priority.
