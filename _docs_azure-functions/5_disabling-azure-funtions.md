---
title: "Disabling the Azure Functions Integration"
---
If you decide to disable the Azure Functions integration for any reason, you can accomplish this from the "Integration Settings" page in your settings.

You'll need to find the Azure Functions integration in your list of integrations, and click "Edit Settings". You'll be taken to a page that shows the current status of your Azure Functions connection, a place to update the Service Principal, and a red box at the bottom to disconnect from Azure Functions.

![Screenshot showing the Disconnect screen for disabling the Azure Functions integration](https://res.cloudinary.com/snyk/image/upload/c_scale,q_auto,w_auto/v1534678294/serverless-docs/azure-disconnect.png)

If you choose to disconnect, your Azure Functions credentials will be removed from Snyk and any Azure Functions projects we had been monitoring will be deactivated on Snyk.

If you choose to re-enable the Azure Functions integration at any time, you'll need to re-enter your Service Principal and activate your projects.