---
title: ""
---

Snyk's Azure Function Apps integration lets you monitor the deployed code of your Node.js Azure Function Apps for any known vulnerabilities found in the application's dependencies, testing at a frequency you control.

For each test, Snyk will communicate directly with Azure to determine exactly what code is currently deployed and what dependencies are being used. Each dependency will in turn be tested against Snyk's vulnerability database to see if it contains any known vulnerabilities. 

If vulnerabilities are found, you will be alerted (via email or Slack) so that you can take immediate action.

In order to turn on the Azure Function Apps integration you'll need to:

1. [Connect to Azure](#connecting-snyk-to-azure-functions) from the integrations page
2. [Add your Azure account credentials](#generating-your-azure-service-principal) to Snyk
3. [Select the projects you want to monitor](#adding-azure-functions) and click "Add to Snyk"