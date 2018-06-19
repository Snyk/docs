---
title: "Setting up your Jira integration"
---

To connect your Snyk account to your Jira account, go to the integrations page in your organisation settings and type in your credentials. We recommend setting up a new user in Jira for this, rather than using existing credentials.

Once you’ve set up the connection, visit one of your Snyk projects. You’ll now see a new button at the bottom of each vulnerability and license issue card that allows you to create a Jira issue.

![Button to create a Jira issue](https://res.cloudinary.com/snyk/image/upload/c_scale,q_auto/v1529413402/docs/jira-integration/create-issue-button.png)

When you click on this, a modal will open with the details about the vulnerability copied across into the relevant fields. You can review and edit this before creating the issue.

Select which Jira project you’d like to send the issue to. The fields that we display below are based on the fields that project has, so switching between projects may show different options.

![Modal to create a Jira issue](https://res.cloudinary.com/snyk/image/upload/c_scale,q_auto/v1529413375/docs/jira-integration/create-issue-modal.png)

Once you’ve created a Jira issue, the Jira key with a link will display on the issue card. If you’re using the Jira API, you can generate multiple Jira issues for the same issue in Snyk.

![Button with Jira key](https://res.cloudinary.com/snyk/image/upload/c_scale,q_auto/v1529413388/docs/jira-integration/jira-key.png)

You can also see which Jira issues have been created from the Issues view in your reports.

![Jira key in reports](https://res.cloudinary.com/snyk/image/upload/c_scale,q_auto/v1529413369/docs/jira-integration/jira-key-in-reports.png)
