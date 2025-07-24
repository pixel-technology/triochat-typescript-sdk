# TriochatSdk TypeScript SDK 1.0.0

Welcome to the TriochatSdk SDK documentation. This guide will help you get started with integrating and using the TriochatSdk SDK in your project.

## Versions

- API version: `1.0.0`
- SDK version: `1.0.0`

## About the API

send message SDK

## Table of Contents

- [Setup & Configuration](#setup--configuration)
  - [Supported Language Versions](#supported-language-versions)
  - [Installation](#installation)
- [Setting a Custom Timeout](#setting-a-custom-timeout)
- [Sample Usage](#sample-usage)
- [Services](#services)
- [Models](#models)

# Setup & Configuration

## Supported Language Versions

This SDK is compatible with the following versions: `TypeScript >= 4.8.4`

## Installation

To get started with the SDK, we recommend installing using `npm`:

```bash
npm install @triochat/triochat-sdk
```

## Setting a Custom Timeout

You can set a custom timeout for the SDK's HTTP requests as follows:

```ts
const triochatSdk = new TriochatSdk({ timeout: 10000 });
```

# Sample Usage

Below is a comprehensive example demonstrating how to authenticate and call a simple endpoint:

```ts
import { SdkSendMessageDto, TriochatSdk } from "@triochat/triochat-sdk";

(async () => {
  const triochatSdk = new TriochatSdk({});

  const sdkSendMessageDto: SdkSendMessageDto = {
    countryCode: "country_code",
    phoneNumber: "phone_number",
    messageType: "messageType",
    templateName: "template_name",
    messageText: "messageText",
    components: ["components"],
    context: {},
    mediaMessage: {},
    media: {},
  };

  const { data } = await triochatSdk.sdk.sdkControllerSendMessage(
    sdkSendMessageDto
  );

  console.log(data);
})();
```

## Services

The SDK provides various services to interact with the API.

<details>
<summary>Below is a list of all available services with links to their detailed documentation:</summary>

| Name                                               |
| :------------------------------------------------- |
| [SdkService](documentation/services/SdkService.md) |

</details>

## Models

The SDK includes several models that represent the data structures used in API requests and responses. These models help in organizing and managing the data efficiently.

<details>
<summary>Below is a list of all available models with links to their detailed documentation:</summary>

| Name                                                           | Description |
| :------------------------------------------------------------- | :---------- |
| [SdkSendMessageDto](documentation/models/SdkSendMessageDto.md) |             |

</details>
