---
name: gemini-3-gas-library
description: Expert assistant for the Gemini 3 Google Apps Script (GAS) library. Use when building Google Workspace add-ons or scripts that require Gemini AI integration, multimodal support, persistent chat sessions, or advanced features like Thinking Mode and Tool Grounding.
---

# Gemini 3 Google Apps Script Library

This skill enables Gemini CLI to help users integrate the Gemini 3 API into Google Apps Script projects. It provides instructions for usage, code snippets for common tasks, and the full implementation of the library for manual installation.

## Installation & Setup

1. **Option A: Add as Library**
   - In your GAS project, click **Libraries +**.
   - Enter Script ID: `1Afd9nLsjiIC_B-OKXdmYM9fFzBUM2YqkLuISVE7z7ABuHh2GxpBFIvdw`.
   - Select version 2 and identifier `GeminiApp`.

2. **API Key Setup**
   - Set your API key in **Project Settings > Script Properties** with the name `GEMINI_API_KEY`.

## Core Workflows

### 1. Initialization
Users can initialize the library using an API key or by relying on Script Properties (`GEMINI_API_KEY`).

```javascript
// With explicit key
const gemini = GeminiApp.init("YOUR_API_KEY");

// Using Script Properties (preferred)
const gemini = GeminiApp.init();
```

### 2. Multi-turn Chat (Persistent)
The library handles state management automatically.

```javascript
const chat = GeminiApp.newPersistentChat("user-session-id");
const response = chat.sendMessage("Tell me about the project.");
```

### 3. Multimodal Requests
Easily attach files from Google Drive or GAS Blobs.

```javascript
const file = DriveApp.getFileById("ID");
const response = gemini.newRequest()
  .addText("Analyze this image.")
  .addDriveFile(file)
  .send();
```

### 4. Advanced Features
- **Thinking Mode**: `.setThinking("high")` (levels: minimal, low, medium, high).
- **Media Resolution**: `.setMediaResolution("high")`.
- **JSON Mode**: `.setResponseJson(schema)`.
- **Tools**: `.enableCodeExecution()` and `.enableGoogleSearch()`.

## Troubleshooting & Resilience
The library includes built-in exponential backoff for `429` (Rate Limit) and `5xx` errors. It automatically handles large file uploads via the Gemini File API when necessary.
