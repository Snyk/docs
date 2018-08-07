---
title: ""
---

Snyk can be used with private source code management systems (SCMs) such as GitHub Enterprise installations via an [applicative tunnel](https://github.com/snyk/broker), referred to as the Snyk "Broker". A Snyk Broker allows moderated access to a private SCM deployment, securely connecting Snyk to your locally managed code repositories. It keeps sensitive data such as your access tokens within the perimeter of your private network, while narrowing down SCM access to the bare minimum required for Snyk.

These instructions will get you up and running with a Snyk Broker, allowing your private SCM to connect to Snyk.io.

Snyk Broker currently supports the following SCMs:
* GitHub Enterprise
* GitHub.com
* Bitbucket Server
* GitLab.com
* On-premise GitLab deployment
* On-premise Jira

### How it works

The Snyk Broker is made up of two web servers that proxy requests over a secure web socket connection. The Broker client runs within your network, in a location with connectivity to your private SCM. On start-up it establishes a secure web socket connection to a Broker server running at https://broker.snyk.io. Requests from Snyk to your private SCM and web-hook initiated requests from your private SCM to Snyk are sent over this tunnel.

The Broker client has a white list of allowed requests (expressed as a JSON file), ensuring that only requests which are required for Snyk to function are proxied. All other requests are dropped. Requests are filtered on both request path, and JSON body.

The default provided white list allows only the following requests:
- Snyk.io is only allowed to fetch dependency manifest files and the Snyk policy file. All other requests are dropped.
- SCM web-hooks are only allowed if they notify of a relevant event (push to branch, pull request opened), AND the event data includes a dependency manifest file or a Snyk policy file. All other web-hooks are dropped.
