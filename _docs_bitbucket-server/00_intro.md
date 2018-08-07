---
title: ""
---

Snyk's Bitbucket Server integration lets you monitor the source code of your repos for any known vulnerabilities found in the application's dependencies, testing at a frequency you control.

**This integration only works with Bitbucket Server instances that are publicly reachable (not on a private network) and not for bitbucket.org. For private instances, you will need to set up via [Snyk's Broker](https://snyk.io/docs/snyk-broker#bitbucket-server-setup).**

For each test, Snyk will communicate directly with Bitbucket Server to determine exactly what code is currently pushed and what dependencies are being used. Each dependency will in turn be tested against Snyk's vulnerability database to see if it contains any known vulnerabilities.

If vulnerabilities are found, you will be alerted (via email or Slack) so that you can take immediate action.

In order to turn on the Bitbucket Server integration you'll need to:

1. [Contact support@snyk.io](mailto:support@snyk.io) and ask us to enable Bitbucket Server support
2. [Connect to Bitbucket Server](#connecting-snyk-to-bitbucket-server) from the Integrations page
3. [Add your Bitbucket Server account credentials](#generating-your-bitbucket-server-credentials) to Snyk
4. [Select the projects you want to monitor](#adding-bitbucket-server-repositories-to-snyk) and click "Add to Snyk"
