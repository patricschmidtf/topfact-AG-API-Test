# Info Controller

Welcome to the **topfact AI Support API** documentation for the `InfoController`. This controller is designed to provide information about the current version of the API.

## Table of Contents

- [Controller Overview](#controller-overview)
- [API Endpoints](#api-endpoints)
  - [Get API Version](#get-api-version)
- [Error Handling](#error-handling)
- [Usage Examples](#usage-examples)


## Controller Overview

The `InfoController` in the topfact AI Support API offers a simple endpoint that allows users to retrieve the version number of the current API assembly.

### Key Features

- **Version Information:** Retrieve the version number of the API assembly for debugging or tracking purposes.

## API Endpoints

### Get API Version

- **URL:** `/api/info`
- **Method:** `GET`
- **Description:** This endpoint returns the version of the currently deployed API assembly.

#### Response Example

**Success (200 OK):**

```json
{
  "version": "1.0.0.0"
}
```

On a successful request, the API will return the version string in the format `major.minor.build.revision`, which reflects the currently running build of the API.

### Example Response

On success, the API will respond with the current version number:

```json
{
  "version": "1.0.0.0"
}
```

## Error Handling

The `InfoController` is a simple endpoint that typically returns a `200 OK` status. However, in case of internal server issues, it might respond with a `500 Internal Server Error`.

- **500 Internal Server Error:** Indicates that an error occurred while fetching the version.

```json
{
  "status": "ERROR",
  "message": "An error occurred while retrieving the API version."
}
```

## Usage Examples

### Example Request

To get the current version of the API, you can send a `GET` request to `/api/info`. Here's an example using `curl`:

```bash
curl -X GET https://yourapi.com/api/info
```
