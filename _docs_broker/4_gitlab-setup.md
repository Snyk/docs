---
title: "Gitlab setup"
---

In order to interact with your Gitlab projects, Snyk needs to use an access token with an `api` scope. The access token must be provided to the broker client, which then identifies with these credentials on requests as they are proxied from Snyk to your Gitlab deployment.

*The Gitlab access token never leaves your network!*
