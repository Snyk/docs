---
title: How to integrate GitHub to test and watch your repositories
---

You can add your Node.js, Ruby, Python, Scala and Java GitHub repos and quickly test them, or decide which ones you’d like to continously watch with Snyk.

![Adding your GH repos](http://res.cloudinary.com/snyk/image/upload/w_800/v1493817321/docs/choose_github_repos.png)

1. Go to the [integrations](https://snyk.io/integrations) page and click "Connect to GitHub".
2. You need to grant Snyk additional GitHub permissions. Choose to give access to public and private repositories, or grant access to public repositories only.
3. Next, you’ll see a list of all GitHub repos across your GitHub organisations. Select the repos you would like to test with Snyk. If you have supported manifest files at the root, or one or two directories deep, Snyk will automatically recognize and create projects for them.
4. Click on the button at the bottom of the page "Add selected repositories to Snyk". The selected repos appear in your projects, and will be continuously checked for vulnerabilities.
5. Clicking "View report" on any project lets you view & fix vulnerabilities right away. You'll be able to review the suggested remediations, and create a PR with the required upgrades or patches.

<div class="alert alert--inline alert--notice"><p class="alert__text">To view your organisation's projects in Snyk, you'll need to have <a href="#authorizing-github">sufficient access</a> to your organisation's repositories on GitHub.</p></div>
