---
title: About known vulnerabilities
---

### What are known vulnerabilities?

Known vulnerabilities are publicly disclosed security bugs, typically found and logged by users, or reported by security researchers. Being public makes these issues the easiest ones for attackers to find and exploit <sup><a href="http://www.theregister.co.uk/2015/02/23/hp_hack_vulnerable_threat_study/">[1]</a></sup>, and therefore very important to address.

### New stuff

It's awesome!

### What are direct and deep dependencies?

Known vulnerabilities can be introduced either via a direct or via a deep dependency.

* A direct dependency is a package that you've included in your own project via package.json or Gemfile.
* A deep dependency, also referred to as an indirect, chained, or transitive dependency, is a package that you are not using directly, but one that is used by one of your direct dependencies.

In other words, if your application is using package A, and package A is using package B, then your application is indirectly depending on package B. And if package B is vulnerable, you are vulnerable.

### How do you determine the severity of a vulnerability?

The severity of a vulnerability is manually assigned by our security research team. It’s based primarily on the impact of the vulnerability, and by how easy it is to exploit it.

For instance, the [bassmaster vulnerability](https://snyk.io/vuln/npm:bassmaster:20140927) allows an attacker to execute code on your server (a “remote command execution” vulnerability), and can easily be exploited with a well crafted request, making it a high severity issue. The [dns-sync vulnerability](https://snyk.io/vuln/npm:dns-sync:20141111) also allows remote command execution, but to exploit it an attacker needs to control the name of the host you resolve - a less likely scenario. Therefore, it was deemed medium severity.

### Why should I monitor my projects for known vulnerabilities?

New vulnerabilities aren’t actually new security holes - they’re newly disclosed, but impact old, existing code. This means you could have new known vulnerabilities without making any code changes. [Watching your GitHub repos](https://snyk.io/docs/github/#how-to-integrate-github-to-test-and-watch-your-repositories) or [local projects](https://snyk.io/docs/using-snyk/#monitor) means you’ll be the first to know if you are affected by a newly disclosed vulnerability, and you can assess and act upon the vulnerability risk quickly.
