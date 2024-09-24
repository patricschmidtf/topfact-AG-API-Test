# Client Initialization Logic

This repository contains the implementation of the `ClientInitializationLogic` class, which is responsible for initializing the Azure OpenAI client with the necessary configuration settings and secrets.

## Overview

The `ClientInitializationLogic` class provides methods to validate and create a client instance for communication with Azure OpenAI services. It ensures that all required parameters are provided and logs appropriate error messages when they are missing.

## Class: ClientInitializationLogic

### Constructors

#### `ClientInitializationLogic(ILogger<ClientInitializationLogic> logger, Settings settings, Secrets secrets)`

Initializes a new instance of the `ClientInitializationLogic` class.

**Parameters:**

- `ILogger<ClientInitializationLogic> logger`: The logger for logging error and information messages.
- `Settings settings`: An instance of the `Settings` class containing configuration settings.
- `Secrets secrets`: An instance of the `Secrets` class containing sensitive information such as API keys and endpoints.

**Throws:**

- `ArgumentNullException`: If any of the parameters (`logger`, `settings`, or `secrets`) are `null`.

### Methods

#### `AzureOpenAIClient InitializeAzureClient()`

Initializes and returns an instance of the `AzureOpenAIClient`.

**Returns:**

- `AzureOpenAIClient`: A client configured to interact with Azure OpenAI services.

**Throws:**

- `ArgumentNullException`: If the `endpoint` or `openAiApiKey` properties of the `_secrets` instance are `null` or empty. An error message is logged before throwing the exception.

**Example:**

```csharp
var clientInitializationLogic = new ClientInitializationLogic(logger, settings, secrets);
AzureOpenAIClient azureClient = clientInitializationLogic.InitializeAzureClient();
