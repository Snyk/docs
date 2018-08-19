---
title: Adding Azure Functions to Snyk
---
Once you've successfully connected Snyk to your Azure account, you'll be able to select Azure functions that you would like Snyk to monitor. You can do this either using the "Add projects" button on the integrations page, or directly from the Azure Functions integration settings page.

In either case, you'll see a list of any available Function apps on the Azure account you connected. Select the ones you want to monitor and click the "add to Snyk" button.

![Screenshot of the screen displaying the available Azure Functions to monitor](https://res.cloudinary.com/snyk/image/upload/w_auto,c_scale,q_auto/v1534678294/serverless-docs/azure-functions-to-test.png)

As soon as you've added the projects to Snyk, Snyk will test them and begin to display a list of all monitored Azure functions in your [project dashboard](https://app.snyk.io/projects). You'll also see a snapshot of any current vulnerabilities, and be able to click through for a more detailed report including any steps to remediate.

![Screenshot of the screen displaying the Azure Functions](https://res.cloudinary.com/snyk/image/upload/w_auto,c_scale,q_auto/v1534678295/serverless-docs/azure-projects.png)

Snyk will now continuously monitor each of those functions for known vulnerabilities. You can add more functions at any time.
