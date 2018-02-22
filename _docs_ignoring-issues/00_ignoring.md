---
title: "Ignoring issues"
---

Ignoring security issues shouldn't be the default action, but it is sometimes necessary. The best practice is to fix or patch vulnerabilities, or to remove the vulnerable dependency, but there may still be reasons why you would want to suppress an issue – for example, if an issue doesn't currently have a fix, you might want to snooze it until it does.  

Some issues are irrelevant for certain projects (e.g. a DDOS attack for an internal service). Other times, an issue has a path that makes it non-exploitable. In these scenarios Snyk would still recommend fixing the issue where possible, as just because the vulnerability is not exploitable today via the current code paths, it does not mean it will not be in the future if the code changes. 

Issues can be ignored and viewed via the snyk.io UI using the issue filter on your project, via the Snyk APIs and via the cli. 
