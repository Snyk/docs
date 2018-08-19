---
title: Generating your Azure Service Principal
---
To give Snyk access to your Azure account, you'll need a valid Service Principal.

To create a Service Principal for use by Snyk, you can either use the [Azure Portal](https://portal.azure.com/) or the [Azure CLI 2.0](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli).

After installing the Azure CLI 2.0, you should have the `az` command. Authenticate the CLI with your account using:

```bash
az login
```

Once authenticated, use it to create the Service Principal:

```bash
az ad sp create-for-rbac --name SpNameExample --password SpPasswordExample --role Reader
```

This would result in JSON output similar to the following, which contains the Service Principal `name`, `password` and `tenant` that you'll need for setting up Snyk:

```json
{
  "appId": "f5f1ce7d-c247-42e6-91a4-ad1e7example",
  "displayName": "SpNameExample",
  "name": "http://SpNameExample",
  "password": "SpPasswordExample",
  "tenant": "874186fd-a7a8-4e98-9b9e-3df00example"
}
```

From there you can login to your Snyk account and paste in your `name`, `password` and `tenant`.

More information on creating a Service Principal for Azure can be found in Azure's documentation:

[CLI](https://docs.microsoft.com/en-us/cli/azure/create-an-azure-service-principal-azure-cli)

[Portal](https://docs.microsoft.com/en-us/azure/azure-resource-manager/resource-group-create-service-principal-portal)