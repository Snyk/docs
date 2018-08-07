---
title: "GitHub / GitHub Enterprise setup"
---

In order to interact with your GitHub.com or GitHub Enterprise repositories, Snyk needs to use a personal access token with "repo" and "admin:repo_hook" scopes.

To create a GitHub personal access token:

 1. log in to your GitHub.com or GitHub Enterprise account
 2. navigate to "/settings/tokens" in your web browser. e.g. for GitHub.com, go to [https://github.com/settings/tokens](https://github.com/settings/tokens)
 3. click on the "Generate new token" button
 4. enter a description for the token, and select the "**repo**" and "**admin:repo_hook**" scope
 5. click on the "Generate token" button
 6. securely save the token so that you can configure your Broker client with it

This GitHub token must be provided to the Broker client, which then identifies with it on requests as they are proxied from Snyk to your GitHub.com or GitHub Enterprise.

*The GitHub token never leaves your network!*
