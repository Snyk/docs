---
title: Configure Bitbucket Pipelines
---

After running the steps above to create a `.snyk `policy file, you now need to create a `bitbucket-pipelines.yml` file which will configure Bitbucket Pipelines.

If you aren't using Pipelines yet, go to Bitbucket, add the Bitbucket Pipelines add-on, and enable it for the repository in question.

### Creating a new bitbucket-pipelines.yml file

Use the `bitbucket-pipelines.yml` from [the snyk-pipelines repository](https://bitbucket.org/snyk/snyk-pipelines/src/).

This file has the configuration we recommend to stay secure:

* `snyk protect` applies any patches you chose during `snyk wizard`.
* `snyk test` will automatically run as part of `npm test` and will fail the pipeline if any known vulnerabilities are found in the dependencies.
* Snyk alerts you when newly disclosed vulnerabilities affect your project's dependencies. `snyk monitor` makes sure we have an up-to-date list of your dependencies to do so accurately. You'll also need to authenticate to Snyk, so we know where to update the dependencies.

As part of setup, you need to configure your environment to include the `SNYK_TOKEN` environment variable in the Bitbucket settings. You can find your API token in your [account settings on snyk.io](https://app.snyk.io/account/).

![Configuring the environment variable](https://res.cloudinary.com/snyk/image/upload/c_scale,w_500/v1475078005/Configure_env_var_on_BB.png)
*Configuring the environment variable*

### Adapting an existing bitbucket-pipelines.yml file

If you want to adapt an existing `bitbucket-pipelines.yml` file, we recommend to add Snyk like this:

```yaml
- npm install
# authenticate with snyk
- node node_modules/snyk/cli auth ${SNYK_TOKEN} -d
# run snyk protect to apply any patches
- node node_modules/snyk/cli protect
# snyk test will run as part of npm test and fail if it finds vulnerabilities
- npm test
# snyk monitor updates the dependencies Snyk will monitor for new vulnerabilities
- if [ $BITBUCKET_BRANCH == "master" ]; then node node_modules/snyk/cli monitor; fi;
```
You'll need to configure your environment to include the `SNYK_TOKEN` environment variable. You can find your API token in your [account settings on snyk.io](https://app.snyk.io/account/). 
