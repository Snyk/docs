---
title: ""
---

**Snyk Runtime Protection is currently in Beta. It is available for NodeJS and Java applications. Please reach out to [runtime@snyk.io](mailto:runtime@snyk.io) if you'd like Beta access.**

Snyk Runtime Protection provides application security monitoring in your application's runtime environment. Instrument your application with a Snyk runtime agent to track your application dependencies.

Snyk Runtime Protection highlights exploitable vulnerabilities in your application dependencies. With this data, you can focus your remediation efforts where they matter the most.

![A vulnerability with runtime information inside](https://res.cloudinary.com/snyk/image/upload/c_scale,q_auto,w_800/v1542023032/docs/runtime/runtime-issue-card.png)

_A vulnerability that is called in runtime. The vulnerable functions are listed._

The Snyk runtime agent inspects every dependency of your application. It creates an execution hook on vulnerable functions in relevant dependencies. Using these hooks, the agent detects actual use of vulnerable functions. The agent sends this data in beacons to Snyk, adding to the Snyk project data.

Configure the runtime agent with an ID of a project monitored by Snyk. You can find the ID via the [projects API](https://snyk.docs.apiary.io/#reference/projects/projects-by-organisation/list-all-projects), or by inspecting the settings page of your project.
