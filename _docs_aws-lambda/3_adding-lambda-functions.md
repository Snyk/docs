---
title: Adding Lambda Functions to Snyk
---
Once you've successfully connected Snyk to your AWS Lambda account, you'll be able to select AWS Lambda functions that you would like Snyk to monitor. You can do this either using the "Add projects" button on the integrations page, or directly from the AWS Lambda integration settings page.

In either case, you'll see a list of any available projects on the AWS Lambda account you connected. Select the ones you want to monitor and click the "add to Snyk" button.

![Screenshot of the screen displaying the available AWS Lambda apps to monitor](https://res.cloudinary.com/snyk/image/upload/w_auto,c_scale,q_auto/v1493173601/serverless-docs/aws-functions-to-test.png)

As soon as you've added the projects to Snyk, Snyk will test them and begin to display a list of all monitored AWS Lambda functions in your [project dashboard](https://app.snyk.io/projects). You'll also see a snapshot of any current vulnerabilities, and be able to click through for a more detailed report including any steps to remediate.

![Screenshot of the screen displaying the AWS Lambda projects](https://res.cloudinary.com/snyk/image/upload/w_auto,c_scale,q_auto/v1493173602/serverless-docs/aws-projects.png)

Snyk will now continuously monitor each of those functions for known vulnerabilities. You can add more functions at any time.
