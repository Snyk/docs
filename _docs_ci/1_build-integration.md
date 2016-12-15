---
title: Node.js CI integration
---

To continuously avoid known vulnerabilities in your Node.js dependencies, integrate Snyk into your continuous integration (a.k.a. build) system. Here are the steps required to to so:

1. Install the Snyk utility using `npm install -g snyk`.
2. Run `snyk wizard` in the directory of your project following the prompts which will also generate a `.snyk` policy file. For more information about this, see [our CLI documentation](/docs/using-snyk/#wizard).
3. Ensure the `.snyk` file you generated was added to your source control (`git add .snyk`).
4. If you selected to, Snyk will include `snyk test` as part of your `npm test` command, so if there are new vulnerabilities in the future, your CI will fail, protecting you from introducing vulnerabilities to production. Alternatively, you can add `snyk test` to any other CI test platform you use.

To stay secure over time, Snyk alerts you about newly disclosed vulnerabilities that affect your project's dependencies. 
To make sure the list of dependencies we have for your project is up to date, refresh it continuously by running `snyk monitor` in your deployment process. You'll also need to authenticate to Snyk, so we know where to update the dependencies.

To do both, add the following to your deployment scripts:

```
snyk auth $SNYK_TOKEN
snyk monitor
```

Configure your environment to include the `SNYK_TOKEN` environment variable. You can find your API token in your [account settings on snyk.io](https://snyk.io/account/). 
