# ChatCompletionOptionsConfiguration

## Overview

`ChatCompletionOptionsConfiguration` is a service class designed for configuring chat completion options in an Azure OpenAI integration. It utilizes settings and secrets to dynamically set parameters such as temperature, maximum tokens, and penalties for chat completion requests.

## Features

- Configures chat completion options for Azure OpenAI.
- Integrates Azure Cognitive Search as a data source for enhanced query capabilities.
- Implements logging to capture configuration issues.

## Dependencies

- `Azure.AI.OpenAI`
- `OpenAI.Chat`
- `topfact.AI.SupportAPI.Models`
- `Microsoft.Extensions.Logging`

## Constructor

```csharp
public ChatCompletionOptionsConfiguration(ILogger<ChatCompletionOptionsConfiguration> logger, Settings settings, Secrets secrets)
```

### Parameters

- `logger`: An instance of `ILogger<ChatCompletionOptionsConfiguration>` for logging.
- `settings`: An instance of `Settings` containing configuration values for chat completion.
- `secrets`: An instance of `Secrets` containing sensitive data like API keys and endpoints.

## Methods

### ConfigureChatCompletionOptions

```csharp
public ChatCompletionOptions ConfigureChatCompletionOptions()
```

#### Returns

Returns an instance of `ChatCompletionOptions` configured with parameters such as:
- `Temperature`: Controls randomness in responses.
- `TopP`: An alternative to temperature sampling.
- `MaxTokens`: The maximum number of tokens to generate.
- `FrequencyPenalty`: Reduces the likelihood of repeating phrases.
- `PresencePenalty`: Increases the likelihood of introducing new topics.

### AddAzureCognitiveSearch

```csharp
public ChatCompletionOptions AddAzureCognitiveSearch(ChatCompletionOptions options)
```

#### Parameters

- `options`: An instance of `ChatCompletionOptions` to which the Azure Cognitive Search data source will be added.

#### Returns

Returns the modified `ChatCompletionOptions` with the Azure Cognitive Search data source included.

#### Exceptions

- Throws `ArgumentNullException` if the search endpoint is null or empty.

## Usage Example

```csharp
var logger = // Get logger instance
var settings = // Load settings
var secrets = // Load secrets

var chatConfig = new ChatCompletionOptionsConfiguration(logger, settings, secrets);
var chatOptions = chatConfig.ConfigureChatCompletionOptions();
chatConfig.AddAzureCognitiveSearch(chatOptions);
```
