# Set Telegram Menu Button

```bash
# Set the menu button for a Telegram bot
portex bot menu set <app-name> <menu-url>
```

## Description

The `portex bot menu set` command is used to set the menu button for a specified Telegram bot associated with a given application. This command allows users to update the menu button URL for the bot.

## Parameters

| Type     | Argument/Flag | Description                                                                 | Required |
| -------- | ------------- | --------------------------------------------------------------------------- | -------- |
| **Args** | `<app-name>`  | **Required**: The name of the application for which to set the menu button. | Yes      |
| **Args** | `<menu-url>`  | **Required**: The URL that the menu button will link to.                    | Yes      |

## Example

```bash
# Set the menu button for the application named "MyApp" with the URL "http://example.com/menu"
portex bot menu set MyApp http://example.com/menu
```

## Success and Failure Messages

- **Success**: If the menu button is updated successfully, you will see the following message:

  - `Menu button updated successfully`

- **Failure**: If an error occurs during the update process, you will see the following message:
  - `Failed to update menu button`
  - If the application is not bound to a Telegram Bot, the following message will be displayed:
    - `Telegram Application is not bound to a Telegram bot. Please use 'portex bot register <application_name> <bot_token>' to bind a Telegram bot before setting the menu.`
  - If the platform is not Telegram, the following message will be displayed:
    - `Only Telegram Application supports.`

## Notes

- **Platform Support**: The `portex bot menu set` command is only supported for applications bound to the Telegram platform.
- **Error Handling**: Make sure to handle any potential errors during the update process to provide appropriate feedback.
