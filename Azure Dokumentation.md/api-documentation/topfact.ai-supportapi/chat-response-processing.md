# topfact.AI.SupportAPI

This repository contains the implementation of the `topfact.AI.SupportAPI` namespace, which is designed to process chat responses using Azure OpenAI services. It provides functionality for logging intents, creating user messages, and extracting citation GUIDs from chat responses.

## Overview

The `ChatResponseProcessing` class is responsible for handling user messages and logging intents, along with extracting relevant citation information from chat completions. This class leverages Azure's AI capabilities to enhance user interaction and provide accurate support.

## Features

- **Create User Messages**: Constructs a user message based on the provided input, including the user's name, product, and question.
- **Log Detected Intents**: Logs the intent detected from user input for monitoring and analytics purposes.
- **Extract Citation GUIDs**: Parses citations from chat responses to extract relevant GUIDs, adding them to a refined data model for further processing.

## Installation

To use this library, ensure you have the necessary packages installed. You can do this via NuGet:

```bash
dotnet add package Azure.AI.OpenAI
```

## Usage

### Creating a User Message

To create a user message, instantiate the `ChatResponseProcessing` class and call the `CreateUserMessage` method with a `CompletionRequest` object.

```csharp
var processingService = new ChatResponseProcessing(logger, settings, secrets);
var userMessage = processingService.CreateUserMessage(new CompletionRequest
{
    UserName = "John Doe",
    Product = "Example Product",
    Prompt = "How do I reset my password?"
});
```

### Logging Intent

To log a detected intent, you can use the `LogIntent` method.

```csharp
processingService.LogIntent("ResetPassword");
```

### Extracting Citation GUIDs

You can extract citation GUIDs from chat completions by calling the `ExtractCitationsGuid` method.

```csharp
var citations = new List<AzureChatCitation>
{
    new AzureChatCitation { Content = "{"PageGuid":"123e4567-e89b-12d3-a456-426614174000"}" }
};

var manipulatedCompletion = new ChatCompletionRefinedData();
processingService.ExtractCitationsGuid(citations, manipulatedCompletion);
```

## Contributing

Contributions are welcome! Please submit a pull request or open an issue for any enhancements or bug fixes.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contact

For support or inquiries, please contact [your-email@example.com].
