---
title: "Ignoring issues"
---

Ignoring security issues shouldn't be the default action, but it is sometimes necessary. Snyk only validates vulnerabilities that exist in dependent components, so it has a relatively low false-positive rate (which should reduce the need to ignore), but there are still reasons why you may wish to suppress an issue – for example, if an issue doesn't currently have a fix, you might want to snooze it until it does.

Some issues are irrelevant for certain projects (e.g. a DOS attack for an internal service). Other times, an issue has a path that makes it non-exploitable.

Ignored issues are available to view (and edit) in our UI via the issue filter on your project, and you can also initiate them via the `.snyk` policy file. If you use our API, ignore information is also included there.
