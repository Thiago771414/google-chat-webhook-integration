# Webhook Notification Integration with Google Chat

![Project Type](https://img.shields.io/badge/Project%20Type-Integration%20Architecture%20Case%20Study-purple)
![Architecture](https://img.shields.io/badge/Pattern-Webhooks-blue)
![Integration](https://img.shields.io/badge/System-Google%20Chat-green)
![Messaging](https://img.shields.io/badge/Type-Async%20Notification-orange)
![Automation](https://img.shields.io/badge/Automation-Apps%20Script-yellow)

---

<p align="center">
  <img src="https://raw.githubusercontent.com/Thiago771414/imagensProjetos/main/slices/mobile/googlewebhook.png" width="900">
</p>

---

# Webhook Notification Architecture

This repository demonstrates how to send asynchronous notifications to **Google Chat using incoming webhooks**.

Webhooks are widely used in modern backend systems to notify external services when specific events occur.

Typical examples include:

- monitoring alerts
- CI/CD notifications
- payment events
- system failures
- deployment updates

This repository serves as an **engineering case study for webhook-based integrations**.

---

# Case Study

## Problem

Modern distributed systems need to notify external services when events occur.

Examples:

- a server becomes unavailable
- a deployment finishes
- a monitoring alert is triggered
- a system error occurs

Without webhook integrations, these events require manual monitoring or polling systems.

---

## Solution

Webhooks allow applications to send **event-driven notifications** to external platforms such as Google Chat.

This repository demonstrates how to:

- configure incoming webhooks
- send HTTP POST notifications
- integrate monitoring or automation scripts
- trigger team alerts in real-time

---

# Architecture

Typical webhook notification architecture:

```text
Monitoring System
│
▼
Event Trigger
│
▼
Webhook Request (HTTP POST)
│
▼
Google Chat Webhook Endpoint
│
▼
Chat Message Notification
```

This architecture allows asynchronous communication between systems.

---

# Webhook Example

Example webhook script sending a message to Google Chat.

```javascript
function webhook() {

const url = "https://chat.googleapis.com/v1/spaces/AAAAGCYeSRY/messages";

const options = {
  method: "post",
  headers: {
    "Content-Type": "application/json; charset=UTF-8"
  },
  payload: JSON.stringify({
    text: "Hello from Apps Script!"
  })
};

const response = UrlFetchApp.fetch(url, options);

Logger.log(response);

}
```
The webhook sends a POST request containing a JSON payload with the message.

# How Webhooks Work

1️⃣ Event occurs in a system
2️⃣ Application triggers HTTP request
3️⃣ Webhook endpoint receives the payload
4️⃣ Message is posted in Google Chat

This enables real-time notifications across systems.

# Folder Structure

Example project structure:
```text

google-chat-webhook-integration
│
├── scripts
│   └── webhook.gs
│
├── examples
│   └── monitoring-alert.json
│
├── docs
│   └── architecture.png
│
└── README.md
```
# How to Run
1️⃣ Create a Google Chat incoming webhook.

Follow the official documentation:
```text
https://developers.google.com/chat/how-tos/webhooks
```
2️⃣ Copy the webhook URL.

Example:

https://chat.googleapis.com/v1/spaces/.../messages

3️⃣ Replace the URL in the script.

4️⃣ Run the Apps Script function:
```text
webhook()
```
5️⃣ A message will appear in the configured Google Chat space.

# Learning Outcomes

Developers studying this repository will understand:

webhook architecture patterns

HTTP POST integrations

asynchronous notifications

system monitoring alerts

event-driven integrations

# Technologies

Google Chat Webhooks

HTTP

Apps Script

JSON

Event-driven architecture

# Author

Thiago Reis Lima

LinkedIn
```text
https://www.linkedin.com/in/thiago-lima-2a5896166/
```
