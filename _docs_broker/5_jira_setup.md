---
title: "Jira set-up"
---

In order to interact with your Jira instance, Snyk needs to use a user that can access the API.
The credentials for the user must be provided to the broker client,
which then identifies with these credentials on requests as they are proxied from Snyk to your Jira instance.

*The Jira user credentials never leaves your network!*

To generate a new broker UUID Token or view the current one please go to the organization settings page and then
click on "Integrations" on the left menu, scroll down until you see "Jira" in the list and then click on "Edit Settings".
If you are installing the Jira broker for the first time, go to the bottom of the Jira integration settings page and click on "For installation of Jira within a private network".

Here you can configure how Snyk will interact with the Jira instance, click on the the generate button and we will generate
a new broker token for you and you will be able to use it in the broker client.

For more information about setting up and integrating Snyk with Jira, please refer to the [Jira integration documentation](https://snyk.io/docs/jira-integration).

