# 🚀 Triochat SDK — TypeScript SDK for WhatsApp Messaging

Welcome to the **Triochat SDK** — your ultimate tool to seamlessly send **WhatsApp messages** through the Triochat platform, built for developers who value speed, simplicity, and power. 🛠️💬

## 📦 Versions

- **API Version:** `1.0.0`
- **SDK Version:** `1.0.0`

## 🌐 About the SDK

The Triochat SDK empowers developers to integrate WhatsApp messaging directly into their apps and services with minimal setup. Built in TypeScript, it provides robust typings and a developer-friendly interface.

> 🔐 **Authentication:** All requests require a valid token that can be created from the Triochat developer dashboard.  
> ➡️ Create your token here: [https://triochat.io/](https://triochat.io/)

---

## 📚 Table of Contents

- [✨ Features](#-features)
- [⚙️ Setup & Configuration](#️-setup--configuration)
  - [Supported TypeScript Versions](#supported-typescript-versions)
  - [Installation](#installation)
- [⏱️ Custom Timeout](#️-custom-timeout)
- [🚀 Sample Usage](#-sample-usage)
- [🧩 Services](#-services)
- [📦 Models](#-models)
- [🛠️ Support](#️-support)

---

## ✨ Features

- ✅ Send WhatsApp messages with ease
- ✅ Fully typed DTOs with TypeScript support
- ✅ Simple integration and clean API
- ✅ Configurable timeout for requests
- ✅ Developer-friendly structure

---

## ⚙️ Setup & Configuration

### ✅ Supported TypeScript Versions

This SDK supports: `TypeScript >= 4.8.4`

### 📦 Installation

Install the SDK using npm:

```bash
npm install @triochat/triochat-sdk
```

---

## ⏱️ Custom Timeout

Set a custom timeout (in milliseconds) for the SDK's HTTP requests:

```typescript
const triochatSdk = new TriochatSdk({ timeout: 10000 });
```

---

## 🚀 Sample Usage

```typescript
import { SdkSendMessageDto, TriochatSdk } from "@triochat/triochat-sdk";

(async () => {
  const triochatSdk = new TriochatSdk({
    token: "YOUR_TOKEN_HERE", // 👈 Get this from https://triochat.io/
  });

  const sdkSendMessageDto: SdkSendMessageDto = {
    countryCode: "91",
    phoneNumber: "9876543210",
    messageType: "text",
    templateName: "welcome_template",
    messageText: "Hello from Triochat!",
    components: ["button1", "button2"],
    context: {},
    mediaMessage: {},
    media: {},
  };

  const { data } = await triochatSdk.sdk.sdkControllerSendMessage(
    sdkSendMessageDto
  );

  console.log("Message sent successfully:", data);
})();
```

---

## 🧩 Services

The SDK provides various services to interact with the API.

<details>
<summary>Click to view available services:</summary>

| Name                                               |
| :------------------------------------------------- |
| [SdkService](documentation/services/SdkService.md) |

</details>

---

## 📦 Models

The SDK includes models to help structure requests and responses.

<details>
<summary>Click to view available models:</summary>

| Name                                                           | Description             |
| :------------------------------------------------------------- | :---------------------- |
| [SdkSendMessageDto](documentation/models/SdkSendMessageDto.md) | WhatsApp message schema |

</details>

---

## 🛠️ Support

Need help or found a bug?

- 🌐 Visit our website: [https://triochat.io](https://triochat.io)
- 📧 Contact support: support@triochat.io
- 🐛 Found an issue? [Open a GitHub Issue](https://github.com/triochat/triochat-sdk/issues)

---

> Made with ❤️ by the Triochat Team — powering seamless communication, one message at a time.
