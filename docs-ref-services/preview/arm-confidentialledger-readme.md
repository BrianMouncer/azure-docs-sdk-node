---
title: Azure ConfidentialLedger client library for JavaScript
keywords: Azure, javascript, SDK, API, @azure/arm-confidentialledger, confidentialledger
author: joheredi
ms.author: joheredi
ms.date: 04/24/2023
ms.topic: reference
ms.devlang: javascript
ms.service: confidentialledger
---
# Azure ConfidentialLedger client library for JavaScript - version 1.3.0-beta.1 


This package contains an isomorphic SDK (runs both in Node.js and in browsers) for Azure ConfidentialLedger client.

Microsoft Azure Confidential Compute Ledger Control Plane REST API version 2020-12-01-preview.

[Source code](https://github.com/Azure/azure-sdk-for-js/tree/@azure/arm-confidentialledger_1.3.0-beta.1/sdk/confidentialledger/arm-confidentialledger) |
[Package (NPM)](https://www.npmjs.com/package/@azure/arm-confidentialledger) |
[API reference documentation](/javascript/api/@azure/arm-confidentialledger?view=azure-node-preview) |
[Samples](https://github.com/Azure-Samples/azure-samples-js-management)

## Getting started

### Currently supported environments

- [LTS versions of Node.js](https://github.com/nodejs/release#release-schedule)
- Latest versions of Safari, Chrome, Edge and Firefox.

See our [support policy](https://github.com/Azure/azure-sdk-for-js/blob/@azure/arm-confidentialledger_1.3.0-beta.1/SUPPORT.md) for more details.

### Prerequisites

- An [Azure subscription][azure_sub].

### Install the `@azure/arm-confidentialledger` package

Install the Azure ConfidentialLedger client library for JavaScript with `npm`:

```bash
npm install @azure/arm-confidentialledger
```

### Create and authenticate a `ConfidentialLedgerClient`

To create a client object to access the Azure ConfidentialLedger API, you will need the `endpoint` of your Azure ConfidentialLedger resource and a `credential`. The Azure ConfidentialLedger client can use Azure Active Directory credentials to authenticate.
You can find the endpoint for your Azure ConfidentialLedger resource in the [Azure Portal][azure_portal].

You can authenticate with Azure Active Directory using a credential from the [@azure/identity][azure_identity] library or [an existing AAD Token](https://github.com/Azure/azure-sdk-for-js/blob/@azure/arm-confidentialledger_1.3.0-beta.1/sdk/identity/identity/samples/AzureIdentityExamples.md#authenticating-with-a-pre-fetched-access-token).

To use the [DefaultAzureCredential][defaultazurecredential] provider shown below, or other credential providers provided with the Azure SDK, please install the `@azure/identity` package:

```bash
npm install @azure/identity
```

You will also need to **register a new AAD application and grant access to Azure ConfidentialLedger** by assigning the suitable role to your service principal (note: roles such as `"Owner"` will not grant the necessary permissions).
Set the values of the client ID, tenant ID, and client secret of the AAD application as environment variables: `AZURE_CLIENT_ID`, `AZURE_TENANT_ID`, `AZURE_CLIENT_SECRET`.

For more information about how to create an Azure AD Application check out [this guide](/azure/active-directory/develop/howto-create-service-principal-portal).

```javascript
const { ConfidentialLedgerClient } = require("@azure/arm-confidentialledger");
const { DefaultAzureCredential } = require("@azure/identity");
// For client-side applications running in the browser, use InteractiveBrowserCredential instead of DefaultAzureCredential. See https://aka.ms/azsdk/js/identity/examples for more details.

const subscriptionId = "00000000-0000-0000-0000-000000000000";
const client = new ConfidentialLedgerClient(new DefaultAzureCredential(), subscriptionId);

// For client-side applications running in the browser, use this code instead:
// const credential = new InteractiveBrowserCredential({
//   tenantId: "<YOUR_TENANT_ID>",
//   clientId: "<YOUR_CLIENT_ID>"
// });
// const client = new ConfidentialLedgerClient(credential, subscriptionId);
```


### JavaScript Bundle
To use this client library in the browser, first you need to use a bundler. For details on how to do this, please refer to our [bundling documentation](https://aka.ms/AzureSDKBundling).

## Key concepts

### ConfidentialLedgerClient

`ConfidentialLedgerClient` is the primary interface for developers using the Azure ConfidentialLedger client library. Explore the methods on this client object to understand the different features of the Azure ConfidentialLedger service that you can access.

## Troubleshooting

### Logging

Enabling logging may help uncover useful information about failures. In order to see a log of HTTP requests and responses, set the `AZURE_LOG_LEVEL` environment variable to `info`. Alternatively, logging can be enabled at runtime by calling `setLogLevel` in the `@azure/logger`:

```javascript
const { setLogLevel } = require("@azure/logger");
setLogLevel("info");
```

For more detailed instructions on how to enable logs, you can look at the [@azure/logger package docs](https://github.com/Azure/azure-sdk-for-js/tree/@azure/arm-confidentialledger_1.3.0-beta.1/sdk/core/logger).

## Next steps

Please take a look at the [samples](https://github.com/Azure-Samples/azure-samples-js-management) directory for detailed examples on how to use this library.

## Contributing

If you'd like to contribute to this library, please read the [contributing guide](https://github.com/Azure/azure-sdk-for-js/blob/@azure/arm-confidentialledger_1.3.0-beta.1/CONTRIBUTING.md) to learn more about how to build and test the code.

## Related projects

- [Microsoft Azure SDK for JavaScript](https://github.com/Azure/azure-sdk-for-js)

![Impressions](https://azure-sdk-impressions.azurewebsites.net/api/impressions/azure-sdk-for-js%2Fsdk%2Fconfidentialledger%2Farm-confidentialledger%2FREADME.png)

[azure_cli]: /cli/azure
[azure_sub]: https://azure.microsoft.com/free/
[azure_sub]: https://azure.microsoft.com/free/
[azure_portal]: https://portal.azure.com
[azure_identity]: https://github.com/Azure/azure-sdk-for-js/tree/@azure/arm-confidentialledger_1.3.0-beta.1/sdk/identity/identity
[defaultazurecredential]: https://github.com/Azure/azure-sdk-for-js/tree/@azure/arm-confidentialledger_1.3.0-beta.1/sdk/identity/identity#defaultazurecredential
