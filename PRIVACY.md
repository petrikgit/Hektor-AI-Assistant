# Privacy

Hektor is designed to keep AI processing as local and private as possible.

The main idea is simple: your computer runs the AI model and acts as the server for your personal assistant.

## How It Works

- **Local AI:** Hektor uses Ollama to run AI models directly on your computer. AI requests are processed locally instead of being sent to external AI providers.
- **No Cloud Server:** Hektor does not use its own cloud server or remote database.
- **Conversation History:** Conversations are stored locally on your computer using SQLite. Conversation history is currently not encrypted.
- **Telegram:** When using Telegram, messages pass through Telegram's infrastructure and are subject to Telegram's privacy policies.
- **Bot Credentials:** Telegram bot tokens are stored using Windows secure storage where supported.
- **No Tracking:** Hektor does not include analytics or telemetry.

## Important Notes

Although local AI processing helps keep your conversations on your own computer, Telegram communication requires an internet connection and uses Telegram's servers.

Your computer is responsible for running Hektor and the local AI model. Keep your system secure and do not share your Telegram bot token or authorize users you do not trust.

Hektor is still an early project, and privacy and security improvements may be introduced in future versions.

---

**The goal is to keep Hektor as private, independent and affordable as possible.**