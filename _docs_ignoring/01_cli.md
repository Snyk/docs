---
title: "Ignoring issues in the CLI"
---

Suppressing issues is possible via the .snyk policy file, and you’ll see this option any time you run `snyk wizard` on a project and a vulnerability is found. Ignoring the vulnerability adds a record to the .snyk file with the path and given reason (if one was provided). Here's an example:

```
'npm:moment:20170905':
  - moment:
    reason: The reason given
    expires: '2017-12-29T16:10:16.946Z'
```

[More about ignoring issues in the CLI](https://snyk.io/docs/using-snyk#ignore).
