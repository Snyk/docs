---
title: Generating your AWS Lambda Credentials
---
To give Snyk access to your AWS Lambda account, you'll need both a valid Secret Access Key and a valid Access Key ID.

You can find and create Access Key ID's for an IAM user from the [IAM console](https://console.aws.amazon.com/iam/). The Secret Access Key can also be obtained by then downloading the credentials.

Alternatively, you can use the AWS CLI to generate an Access Key ID for a user as well as download the rest of their security credentials. For example, to set a new access Key ID for user 'Bob', you would run the following command:

```
aws iam create-access-key --user-name Bob
```

This would result in JSON output similar to the following, which contains the Secret Access Key that you'll need for setting up Snyk:

```bash
{
    "AccessKey": {
        "UserName": "Bob",
        "Status": "Active",
        "CreateDate": "2015-03-09T18:39:23.411Z",
        "SecretAccessKey": "wJalrXUtnFEMI/K7MDENG/bPxRfiCYzEXAMPLEKEY",
        "AccessKeyId": "AKIAIOSFODNN7EXAMPLE"
    }
}
```

From there you can login to your Snyk account and paste in your Access Key ID and Secret Access Key.

More information on obtaining your security credentials from AWS can be found [in their documentation](https://docs.aws.amazon.com/cli/latest/reference/iam/create-access-key.html).
