---
title: "Ignoring issues in the CLI"
---

Suppressing issues is possible via the CLI. For node.js projects you can use snyk wizard, which will give you the option of ignoring the vulnerability for a period of 30 days. If you want to ignore another supported language or if you want to specify a different duration, you can use the snyk ignore command. 
```
 snyk ignore --id='brace-expansion@1.1.6' --expiry='2018-04-01' --reason='testing'
```

When using snyk wizard or snyk ignore the .snyk policy file is updated with the path and given reason (if one was provided). Here's an example:

```
'npm:moment:20170905':
  - moment:
    reason: The reason given
    expires: '2017-12-29T16:10:16.946Z'
```

[More about ignoring issues in the CLI](https://snyk.io/docs/using-snyk#ignore).
