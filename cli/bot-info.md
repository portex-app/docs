# Manage Telegram Bot for Mini-App

```bash
# Manage bots in the mini-app
portex bot <app-name>
```

## Description

The `portex bot` command is used to manage Telegram bots that are bound to mini-apps. This command retrieves and displays information about the Telegram bot associated with the specified mini-app. The `portex bot` command is only applicable to mini-apps hosted on the Telegram platform.

## Parameters

| Parameter    | Description                                                                                                                                    | Required |
| ------------ | ---------------------------------------------------------------------------------------------------------------------------------------------- | -------- |
| `<app-name>` | The name of the application. This parameter is required and should correspond to the name of the mini-app that you want to manage the bot for. | Yes      |

## Example

```bash
# Display information about the Telegram bot bound to the "MyApp" application
portex bot MyApp
```

## Success and Failure Messages

- **Success**: After successfully retrieving the bot's information, the system will display the following table:

  ```
  +----------------------+------------------------------------------------------------------+-----------------------------------------+
  | name                 | description                                                    | short_description                      |
  +----------------------+------------------------------------------------------------------+-----------------------------------------+
  | MyBot                | This is a bot for MyApp                                         | A short description of MyBot            |
  +----------------------+------------------------------------------------------------------+-----------------------------------------+
  ```

- **Failure**: If the application is not bound to a Telegram bot, an error message will be shown:

  ```
  Telegram Application is not bound to a Telegram bot. Please use 'portex bot register MyApp <bot_token>' to bind a Telegram bot before setting menu.
  ```

  Additionally, if the platform is not Telegram, the following error message will be displayed:

  ```
  Only Telegram Platform Application supports.
  ```

## Notes

- **Platform Support**: The `portex bot` command is only supported for mini-apps that are hosted on the Telegram platform.
- **Bot Registration**: If the mini-app is not bound to a Telegram bot, you can register the bot using the `portex bot register` command, providing the bot token as an argument.

## Additional Information

- **Register a Bot**: If you need to register a Telegram bot for your mini-app, you can use the following command:

  ```bash
  portex bot register <app-name> <bot-token>
  ```

- **Bot Management**: Once the bot is registered, you can manage the bot's settings, including menus and other configurations, using additional bot commands.
