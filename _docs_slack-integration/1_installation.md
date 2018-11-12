---
title: Setup
---

Don't like email? You can set up Slack to receive Snyk's alerts about new vulnerabilities that affect your projects, and about new upgrades or patches that have become available.

You'll get two alerts in Slack:

1: A newly disclosed vulnerability affects you

![Slack Vulnerability Alert Node.js](https://res.cloudinary.com/snyk/image/upload/q_auto,f_auto,w_auto/v1474298426/Slack-Vulnerability-Alert.png)
![Slack Vulnerability Alert Ruby](https://res.cloudinary.com/snyk/image/upload/v1478700599/docs/Slack-alert-Ruby.png)

2: A new upgrade or patch is available for a vulnerability that you previously ignored or patched

![Slack Remediation Alert](https://res.cloudinary.com/snyk/image/upload/q_auto,f_auto,w_auto/v1474298547/Slack-Remediation-Alert.png)

To set it up you will need to generate a Slack webhook. You can either do this via the [Incoming WebHooks app](https://slack.com/apps/A0F7XDUAZ-incoming-webhooks) or by [creating your own Slack app](https://api.slack.com/incoming-webhooks).

Once you have generated your Slack Webhook URL, go to your 'Manage organisation' settings, and simply enter the URL.

![Slack Integration](https://res.cloudinary.com/snyk/image/upload/q_auto,f_auto,w_auto/v1474297920/Slack-Integration-Settings.png)
