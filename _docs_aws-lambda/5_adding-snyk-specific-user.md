---
title: Adding a Snyk-specific user to AWS Lambda
---
We recommend adding a dedicated AWS Identity and Access Management (IAM) user for your Snyk organization. That way if at some point you need to revoke the key for any reason, you can do so without impacting anyone within your organization.

The IAM user only needs one attached policy: `AWSLambdaReadOnlyAccess`.

You can learn more about IAM users on the [AWS documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html).
