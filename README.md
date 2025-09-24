# Puter.js Starter

A minimal frontend-only starter demonstrating Puter Cloud features: authentication, key-value storage (KV), file APIs, static hosting, and AI chat/streaming via the Puter SDK.

## Features
- **Auth**: Sign in with Puter and fetch the current user
- **Storage**: Query available storage space
- **Files**: Create and open files via the Puter filesystem and picker
- **Hosting**: Publish a simple static site to a generated `*.puter.site` subdomain
- **AI**: Ask questions and stream responses using `gpt-5-nano`

## Prerequisites
- A modern browser
- Internet access (loads the SDK from `https://js.puter.com/v2/`)

No build tooling is required.

## Getting Started
1. Open `index.html` in your browser.
2. You should see the Puter.js Starter UI with several buttons and demos.

If your browser blocks some features when opening via the `file://` protocol, serve the folder with a simple static server (any local server is fine) and browse via `http://localhost:...`.

## Usage
- **Sign In**: Click "Sign In" and complete the flow. Status appears in the log area.
- **Get User**: Fetch and show the signed-in user JSON.
- **Storage Space**: Display available storage information.
- **Create File**: Write a new `hello_<timestamp>.txt` file in Puter storage.
- **Open File**: Choose a file via the Puter file picker and display its contents.
- **Publish Site**: Create a temporary directory, write a basic `index.html`, and publish to a generated `https://<subdomain>.puter.site` URL.
- **AI Chat**: Enter a prompt and click "Ask" for a single response, or "Stream" to receive a streaming reply.

## Code Overview
All logic lives inline in `index.html` and interacts with the Puter SDK:
- `puter.auth.*` for authentication
- `puter.fs.*` for space, read/write, and directory operations
- `puter.ui.*` for file picker and optional menubar
- `puter.hosting.*` to create and publish a static site
- `puter.ai.chat(...)` for AI responses (with optional `{ stream: true }`)

## Notes
- The demo references model `gpt-5-nano`. Adjust the model name if your environment requires a different one.
- Publishing creates an ephemeral directory and site; treat it as sample output, not production.
- Errors are surfaced in the on-page log or AI output area.

## Helpful Links
- Puter Developer Docs: `https://developer.puter.com`
- Puter JS SDK (CDN): `https://js.puter.com/v2/`

## License
This starter is provided as-is for demonstration purposes. Use, modify, or integrate as needed.
