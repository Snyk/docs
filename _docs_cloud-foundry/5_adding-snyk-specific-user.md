---
title: Adding a Snyk-specific user to Cloud Foundry
---
We suggest adding a dedicated user to Cloud Foundry for your Snyk org. That way if at some point you need to revoke access for any reason, you can do so without impacting anyone within your org.

The minimum permissions needed in order to integrate with Snyk is the space role of `SpaceAuditor`.

You can create a new user with these permissions  from the command line using the following commands:

```
cf create-user snyk pa55w0rd
cf set-space-role snyk my-example-org development SpaceAuditor
```

You can learn more about how to add another user to your application on the [Cloud Foundry documentation](https://docs.cloudfoundry.org/adminguide/cli-user-management.html).
