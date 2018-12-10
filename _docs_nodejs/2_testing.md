---
title: "Testing Node.js projects"
---
We scan Node.js projects by examining your package.json and lockfile if exists (in case the lockfile doesn't exist we will scan the installed packages, when using the [CLI](/docs/using-snyk/)) to compare the specific versions of every [direct and deep dependency](https://snyk.io/docs/faqs/#about-known-vulnerabilities) in your project against our [npm vulnerability database](/vuln?type=npm).
