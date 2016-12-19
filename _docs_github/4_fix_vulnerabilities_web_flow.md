---
title: Fix vulnerabilities with Snyk pull requests
---

When viewing a Snyk test report for a repo that you own, or when looking at a project that you are watching with Snyk, you’ll see two options for fixing a vulnerability: 

1) **‘Open a fix PR’ link:**
generate a Snyk pull request with the minimal changes needed to fix the vulnerabilities affecting the repo.

2) **'Fix this vulnerability' link:**
generate a Snyk pull request that fixes only this vulnerability.

![Fix button](http://res.cloudinary.com/snyk/image/upload/c_scale,w_774/v1478172579/docs/Fix_vulnerabilities_with_a_pull_request.png)

You can review the vulnerabilities that will be fixed, change your selection, and choose to ignore any vulnerabilties that can't be fixed right now before opening the pull request on the 'Open a fix PR' page. 

Note that patching is only supported for Node.js repos; Ruby vulnerabilities can be fixed with upgrades only.

![Open a fix PR page](https://res.cloudinary.com/snyk/image/upload/v1478172977/docs/Open_a_fix_PR.png)

Snyk fixes your Ruby projects by updating vulnerable dependencies in your Gemfile.lock file. When a fix requires a change to your Gemfile, our fix pull requests will propose these changes. 

When you open a PR via snyk.io, we will give you a heads-up when this is the case:

![Gemfile changes flag](https://res.cloudinary.com/snyk/image/upload/v1482163010/docs/Gemfile-changes-flag.png)

Here’s an example for the pull request:

![Snyk remediation PR](https://res.cloudinary.com/snyk/image/upload/v1478173163/docs/Snyk_fix_PR_example.png)

#### Get a Snyk pull request when newly disclosed vulnerabilities affect you

Whenever a vulnerability is disclosed that affects a repo you’re watching, Snyk will not only email you about it, but also generate a Snyk pull request that addresses the vulnerabilities. You'll receive a pull request similar to the example above.

#### Get a Snyk pull request when new upgrades or patches are available

When no upgrade is available, you can ignore or patch the vulnerability (patching is only available for Node.js projects). When a better remediation option has become available, for example an upgrade for a vulnerability you previously ignored, Snyk notifies you about this via email, and also generates a pull request with the new fix.
