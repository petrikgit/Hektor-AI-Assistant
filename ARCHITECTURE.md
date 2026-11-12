# Hektor – Architecture

This document gives a basic overview of how Hektor works and how its main parts are connected.

Hektor is a Windows desktop application built with Electron, React and TypeScript. It uses Ollama to run AI models locally and Telegram to allow remote communication with the assistant.

The main idea is to keep everything as simple as possible and let the user's computer handle most of the work.

## 1. Technologies Used

Here are the main technologies used in Hektor:

| Technology | Purpose |
|---|---|
| Electron | Runs Hektor as a Windows desktop application. |
| React | Builds the user interface. |
| TypeScript | Used for application logic and safer code. |
| Node.js | Handles background tasks and communication with system services. |
| Ollama | Runs local AI models on the user's computer. |
| SQLite | Stores application settings and local data. |
| Telegram Bot API | Allows users to communicate with Hektor remotely. |

## 2. How Hektor Works

Hektor has three main parts:

- **Desktop application** – The interface where users manage settings, connect services and interact with the assistant.
- **Agent Core** – The part responsible for handling requests, managing conversations, permissions and available tools.
- **AI Provider** – Connects Hektor to Ollama and sends requests to the selected local AI model.

Telegram is an additional way to communicate with the same assistant without needing to open the desktop window.

## 3. Application Structure

### Desktop Application

The desktop application is built with Electron and React.

It provides the main interface and includes:

- Dashboard
- AI settings
- Telegram settings
- Permissions
- General application settings

Electron also allows Hektor to run in the background through the Windows system tray.

### Agent Core

The Agent Core is responsible for handling the assistant's main operations.

It manages incoming requests, conversation context, available tools and communication with the AI provider.

It also works with the permission system to control which actions are allowed.

### Local AI – Ollama

Hektor currently uses Ollama to run AI models locally.

The default recommended model is Qwen 2.5 7B, but users can experiment with other models supported by Ollama.

The default Ollama address is:

`http://127.0.0.1:11434`

AI requests are sent to the local Ollama service instead of a remote AI API.

### Telegram Integration

Telegram allows users to communicate with Hektor remotely.

The application uses the Telegram Bot API and checks whether the sender is authorized before processing messages.

Telegram messages are passed to the same assistant logic used by the desktop application.

This means users can interact with Hektor from their phone while the application is running on their computer.

## 4. Data Storage

Hektor uses SQLite for local application data, including settings and conversation information.

Sensitive credentials, such as the Telegram bot token, are protected using Electron's secure storage functionality where supported by the operating system.

Conversation history is currently stored locally and is not encrypted.

Hektor does not use a remote database or its own cloud server.

## 5. Permissions and Security

Hektor includes a permission system that is intended to control which actions the assistant can perform.

The application also uses Electron's security features and separates the user interface from privileged background operations.

Telegram access is restricted to authorized user IDs, and only private conversations are supported in the current version.

The permission system is still being developed. Not all planned system and file operations are available yet.

## 6. Current Architecture and Future Improvements

Hektor is still an early project, so the architecture will probably change as new features are added.

For now, the main focus is on:

- Improving the local AI experience.
- Adding more useful tools.
- Expanding the permission system.
- Improving Telegram integration.
- Keeping the application simple and privacy-focused.

In the future, I may also experiment with other AI providers, such as OpenAI and Google Gemini. However, local AI and keeping costs as low as possible will remain important priorities.

---

**Hektor 0.1.3**
