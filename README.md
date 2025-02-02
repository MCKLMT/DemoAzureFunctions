# Demo Azure Functions

This project demonstrates the use of Azure Functions for serverless computing.
It contains an Azure Bicep template for infrastructure deployment and a dotnet-isolated function sample.

### Prerequisites

- [.NET SDK 9.0](https://dotnet.microsoft.com/en-us/download)
- [Azure Functions Core Tools](https://github.com/Azure/azure-functions-core-tools/tree/v4.x)
- [Azure CLI](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli)

## Getting Started

1. Clone the repository:
    ```bash
    git clone https://github.com/MCKLMT/DemoAzureFunctions.git
    cd DemoAzureFunctions
    ```

2. Follow the steps in file [deployment_script.cli](deployment_script.cli)

## Project Structure

- [deployment_script.cli](deployment_script.cli): Contains all the steps to deploy the infrastructure and the function from scratch.
- [main.bicep](main.bicep): Contains the Bicep template to deploy the infrastructure only.

## Highligths

- The communication between the Azure Function and the storage account is authentified with Managed Identities

- The Azure Function is configured to host .NET 9 in isolated mode, on Linux

- The Azure Function is in consumption mode.

- 3 role assignments are added à the end of the Bicep file. They are required to authenticate the Azure Functions over the Storage account.

- [Azure Functions Core Tools](https://github.com/Azure/azure-functions-core-tools/tree/v4.x) is used to initiate the creation of the source of the function.

- The dotnet application is published locally and zipped.

- The zip is deployed in a container in a storage account.

- The url of the zip is defined on Azure Functions.

- Finally, we have to "refresh" the Azure Functions manually.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request.

## Licence

This project is licensed under the [MIT License](LICENSE).
