---
title: ""
---

Snyk Runtime Protection extends the Snyk offering to your application's production environment. Instrument your application with a Snyk runtime agent to track the use of dependencies by your application. The agent tracks invocations of vulnerable functions in your dependencies, reporting this data back to Snyk.io.

Snyk Runtime Protection allows you to understand which vulnerable dependencies are at a higher risk of being exploited, focusing your remediation efforts where they matter the most.

Snyk Runtime Protection is available for NodeJS and Java applications.

The Snyk runtime agent inspects each and every dependency of your application in order to create an execution hook, signalling when vulnerable functions are being invoked by the application.

The agent collects indications of such vulnerable functions being called. It does not actively interfere with these calls.

The agent sends beacons to snyk.io, indicating which vulnerable functions were invoked.

The agent is configured with an ID of a project monitored by Snyk. Any type of Snyk project can be used and instrumented with Snyk Runtime Protection. You can obtain your project’s ID via the API or by inspecting the settings page of your project.

Once your applications are instrumented with the runtime agent, please reach out to [support@snyk.io](mailto:support@snyk.io) to initiate onboarding to Snyk Runtime Protection.
