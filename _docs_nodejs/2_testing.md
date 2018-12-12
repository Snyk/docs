---
title: "Testing Node.js projects"
---
We scan Node.js projects by examining your package.json and lockfile (package-lock.json or yarn.lock) if exists (when using the [CLI](/docs/using-snyk/), in case the lockfile doesn't exist we will scan the installed packages) to compare the specific versions of every [direct and deep dependency](/docs/faqs/#about-known-vulnerabilities) in your project against our [npm vulnerability database](/vuln?type=npm).
We ignore development dependencies by default, but they can be included from the [CLI](/docs/using-snyk/).
