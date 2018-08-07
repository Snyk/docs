---
title: "Jira setup"
---

First, create a new user with API access in your Jira instance that can be used by Snyk. These credentials need to be provided to the Broker client, which then identifies with these credentials on requests as they are proxied from Snyk to your Jira instance. Note that **the Jira user credentials never leave your network**.

Next, you'll need to generate a new Broker UUID token. Go to "Integrations" in your org settings area, then click on "Jira" in the list, and "Edit Settings".
If you are installing the Jira Broker for the first time, click on the link "For installation of Jira within a private network".

Here, you can configure how Snyk will interact with the Jira instance. Click "generate" to create a new token for use in the Broker client.

For more information about setting up and integrating Snyk with Jira, please refer to the [Jira integration documentation](https://snyk.io/docs/jira-integration).
