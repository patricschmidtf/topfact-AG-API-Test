
# topfact AI Support API

Welcome to the **topfact AI Support API** documentation! This API provides a robust interface for interacting with the Azure OpenAI service, enabling chat completions and response processing.

## Table of Contents

- [API Overview](#api-overview)
- [Authentication](#authentication)
- [Comunication with 3 services](chat-completion-options-configuration.md)
- [API Endpoints](#api-endpoints)
  - [Get Chat Completions](#get-chat-completions)
- [Error Handling](#error-handling)
- [Usage Examples](#usage-examples)
- [Contributing](#contributing)
- [License](#license)

## API Overview

The topfact AI Support API allows users to send requests for chat completions to the Azure OpenAI service. It processes the request, logs relevant intents, and manages the response, including any citations derived from the completion.

### Key Features

- **Chat Completions:** Get contextual chat responses from the Azure OpenAI service.
- **Logging:** Automatically logs user requests and intents for better tracking and analytics.
- **Error Handling:** Robust error handling for various scenarios.

## Authentication

To use the API, you need valid Azure OpenAI credentials, including:

- `endpoint`: The Azure OpenAI endpoint.
- `openAiApiKey`: The API key for authentication.
- `searchEndpoint`: The endpoint for Azure Cognitive Search.

These credentials should be configured in the application's settings.

## API Endpoints

### Get Chat Completions

- **URL:** `/api/completion`
- **Method:** `POST`
- **Request Body:**

```json
{
  "UserName": "string",
  "Message": "string"
}
```

- **Description:** This endpoint processes a user's message and retrieves a chat completion response.

#### Request Example

```bash
curl -X POST https://yourapi.com/api/completion \
-H "Content-Type: application/json" \
-d '{ "UserName": "john_doe", "Message": "What are the benefits of using Azure OpenAI?" }'
```

#### Response Example

**Success (200 OK):**

```json
{
  "status": "success",
  "data": {
    "response": "Using Azure OpenAI provides several benefits, including...",
    "intent": "GetBenefits",
    "citations": ["source1", "source2"]
  }
}
```

**Error (400 Bad Request):**

```json
{
  "status": "ERROR",
  "message": "Invalid completion request."
}
```

## Error Handling

The API provides detailed error messages to help identify issues:

- **400 Bad Request:** Indicates that the input was invalid or null.
- **500 Internal Server Error:** Indicates that an error occurred during processing.

## Usage Examples

### Example Request

To send a message and get a completion response, you can use the following example:

```json
POST /api/completion
Content-Type: application/json

{
  "UserName": "example_user",
  "Message": "Tell me about Azure's AI capabilities."
}
```

### Example Response

On success, the API will return a structured response containing the chat completion and any associated citations.

## Contributing

We welcome contributions to the topfact AI Support API! Please feel free to open issues or submit pull requests.

## License

This project is licensed under the MIT License.
