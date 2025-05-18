<div align="center">

<img src="./docs/images/icon.png" alt="" align="center" height="64" />

# Azure Functions Pizza API

[![Open project in GitHub Codespaces](https://img.shields.io/badge/Codespaces-Open-blue?style=flat-square&logo=github)](https://codespaces.new/Azure-Samples/serverless-recipes-javascript?hide_repo_select=true&ref=main&quickstart=true)
![Node version](https://img.shields.io/badge/Node.js->=20-3c873a?style=flat-square)

[Overview](#overview) • [Run the sample](#run-the-sample) • [Key concepts](#key-concepts) • [Troubleshooting](#troubleshooting) • [Next steps](#next-steps)

</div>

## Overview

TODO: This sample demonstrates how to... with [Azure Functions](https://learn.microsoft.com/azure/azure-functions/functions-overview?pivots=programming-language-javascript).

![Application architecture](./docs/images/architecture.drawio.png)

This application is made from multiple components:

- A serverless API built with [Azure Functions](https://learn.microsoft.com/azure/azure-functions/functions-overview?pivots=programming-language-javascript).

- TODO ...

### API Endpoints

The Pizza API provides the following endpoints:

| Method | Path | Description |
|--------|------|-------------|
| GET | /api/pizzas | Returns a list of all pizzas |
| GET | /api/pizzas/{id} | Retrieves a specific pizza by its ID |
| GET | /api/toppings | Returns a list of all toppings (can be filtered by category with ?category=X) |
| GET | /api/toppings/{id} | Retrieves a specific topping by its ID |
| GET | /api/toppings/categories | Returns a list of all topping categories |
| GET | /api/orders | Returns a list of all orders in the system |
| POST | /api/orders | Places a new order with pizzas (requires userId) |
| GET | /api/orders/{orderId} | Retrieves an order by its ID |
| DELETE | /api/orders/{orderId} | Cancels an order if it has not yet been started (status must be 'pending') |
| GET | /api/images/{filepath} | Retrieves image files (e.g., /api/images/pizzas/pizza-1.jpg) |

You can view the complete API documentation by opening the [Swagger Editor](https://editor.swagger.io/?url=https://raw.githubusercontent.com/microsoft/open-hack-build-25/blob/pizza-api/src/pizza-api/openapi.yaml) or the [OpenAPI YAML file](openapi.yaml).

## Run the sample

### Prerequisites

- [Node.js LTS](https://nodejs.org/en/download/)
- [Azure Developer CLI](https://aka.ms/azure-dev/install)
- [Git](https://git-scm.com/downloads)
- Azure account. If you're new to Azure, [get an Azure account for free](https://azure.microsoft.com/free) to get free Azure credits to get started. If you're a student, you can also get free credits with [Azure for Students](https://aka.ms/azureforstudents).
- Azure account permissions:
  - Your Azure account must have `Microsoft.Authorization/roleAssignments/write` permissions, such as [Role Based Access Control Administrator](https://learn.microsoft.com/azure/role-based-access-control/built-in-roles#role-based-access-control-administrator-preview), [User Access Administrator](https://learn.microsoft.com/azure/role-based-access-control/built-in-roles#user-access-administrator), or [Owner](https://learn.microsoft.com/azure/role-based-access-control/built-in-roles#owner). If you don't have subscription-level permissions, you must be granted [RBAC](https://learn.microsoft.com/azure/role-based-access-control/built-in-roles#role-based-access-control-administrator-preview) for an existing resource group and [deploy to that existing group](docs/deploy_existing.md#resource-group).
  - Your Azure account also needs `Microsoft.Resources/deployments/write` permissions on the subscription level.

### Cost estimation

Pricing varies per region and usage, so it isn't possible to predict exact costs for your usage.
However, you can use the [Azure pricing calculator](TODO) for the resources below to get an estimate.

- Azure Functions: Flex Consumption plan, Free for the first 250K executions. Pricing per execution and memory used. [Pricing](https://azure.microsoft.com/pricing/details/functions/)
- Azure Blob Storage: Standard tier with LRS. Pricing per GB stored and data transfer. [Pricing](https://azure.microsoft.com/pricing/details/storage/blobs/)
- TODO ...

⚠️ To avoid unnecessary costs, remember to take down your app if it's no longer in use,
either by deleting the resource group in the Portal or running `azd down --purge`.

### Setup development environment

You can run this project directly in your browser by using GitHub Codespaces, which will open a web-based VS Code.

1. [**Fork**](https://github.com/Azure-Samples/serverless-recipes-javascript/fork) the project to create your own copy of this repository.
2. On your forked repository, select the **Code** button, then the **Codespaces** tab, and clink on the button **Create codespace on main**.
   ![Screenshot showing how to create a new codespace](../../docs/images/codespaces.png?raw=true)
3. Wait for the Codespace to be created, it should take a few minutes.

If you prefer to run the project locally, follow [these instructions](../../README.md#use-your-local-environment).

### Deploy Azure resources

Open a terminal in the project root and follow these steps to deploy the Azure resources needed:

```bash
# Open the sample directory
cd samples/pizza-api

# Install dependencies
npm install

# Deploy the sample to Azure
azd auth login
azd up
```

You will be prompted to select a base location for the resources. If you're unsure of which location to choose, select `eastus2`.
The deployment process will take a few minutes.

### Test the application

Once the resources are deployed, you can run the following command to run the application locally:

```bash
npm start
```

TODO: This command will start the Azure Functions application locally. You can test the application by...

```bash
curl -X POST http://localhost:7071/api/hello
```

Alternatively, you can also open the file `api.http` and click on **Send Request** to test the endpoints.

### Clean up

To clean up all the Azure resources created by this sample:

1. Run `azd down --purge`
2. When asked if you are sure you want to continue, enter `y`

The resource group and all the resources will be deleted.

## Key concepts


TODO

## Troubleshooting

If you have any issue when running or deploying this sample, please check the [troubleshooting guide](../../docs/troubleshooting.md). If you can't find a solution to your problem, please [open an issue](https://github.com/Azure-Samples/serverless-recipes-javascript/issues).

## Next steps

Here are some resources to learn more about the technologies used in this sample:

- TODO ...
