# Register Telegram Bot

```bash
# Register Telegram Bot
portex bot register <app-name> <bot-token>
```

## Description

The `portex register` command is used to register a Telegram bot for a specified application. This command allows users to bind a Telegram bot to their application by providing the application name and bot token. It verifies the platform and attempts to register the bot, handling any errors that may occur during the process.

## Parameters

- `<app-name>`: The name of the application to deploy. This parameter is required.
- `<bot-token>`: The token of the Telegram bot. This parameter is also required.

**Tip**: To obtain your bot token, you need to create a new bot using [BotFather](https://t.me/botfather) on Telegram. Follow these steps:

1. Open Telegram and search for "BotFather".
2. Start a chat with BotFather and use the command `/newbot` to create a new bot.
3. Follow the prompts to set a name and username for your bot.
4. Once created, BotFather will provide you with a token. Copy this token and use it in the command.

## Example

```bash
# Register a Telegram bot for the application named "MyApp" with the bot token "123456:ABC-DEF1234ghIkl-zyx57W2P0"
portex register MyApp ‘123456:ABC-DEF1234ghIkl-zyx57W2P0’
```

## Notes

- The command will throw an error if the platform is not 'Telegram', indicating that only the Telegram platform supports this command.
- If the binding fails, an appropriate error message will be displayed.
- **Unbind Bot**: Not supported; the current version does not support unbinding Telegram bots.
