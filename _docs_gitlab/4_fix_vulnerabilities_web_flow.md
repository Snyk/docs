---
title: Fix vulnerabilities with Snyk merge requests
---
<div class="alert alert--inline alert--warning"><div class="alert__content"><p class="alert__message">Currently for Node.js and Ruby only</p></div></div>

When viewing a Snyk test report for a project that you own, or when looking at a project that you are watching with Snyk, you’ll see two options for fixing a vulnerability:

1) **‘Open a fix Merge Request’ link:**
generate a Snyk merge request with the minimal changes needed to fix the vulnerabilities affecting the project.

2) **'Fix this vulnerability' link:**
generate a Snyk merge request that fixes only this vulnerability.

You can review the vulnerabilities that will be fixed, change your selection, and choose to ignore any vulnerabilities that can't be fixed right now before opening the merge request on the 'Open a fix Merge Request' page.

Note that patching is only supported for Node.js projects; Ruby vulnerabilities can be fixed with upgrades only.

![Open a fix Merge Request page](https://res.cloudinary.com/snyk/image/upload/q_auto,f_auto,w_auto/v1519427397/features/gitlab-mr.png)

Snyk fixes your Ruby projects by updating vulnerable dependencies in your Gemfile.lock file. When a fix requires a change to your Gemfile, our fix merge requests will propose these changes.

When you open a merge request via snyk.io, we will give you a heads-up when this is the case.

Here’s an example for the merge request:

![Snyk remediation MR](https://res.cloudinary.com/snyk/image/upload/q_auto,f_auto,w_auto/v1519427398/features/gitlab-fix.png)

#### Get a Snyk merge request when newly disclosed vulnerabilities affect you

Whenever a vulnerability is disclosed that affects a project you’re watching, Snyk will not only email you about it, but also generate a Snyk merge request that addresses the vulnerabilities. You'll receive a merge request similar to the example above.

#### Get a Snyk merge request when new upgrades or patches are available

When no upgrade is available, you can ignore or patch the vulnerability (patching is only available for Node.js projects). When a better remediation option has become available, for example an upgrade for a vulnerability you previously ignored, Snyk notifies you about this via email, and also generates a merge request with the new fix.
