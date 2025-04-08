# Delete Telegram Bot Messages

```bash
# Delete messages of a Telegram bot
portex bot message del <app-name> [keys...]
```

## Description

The `portex bot message del` command is used to delete one or more messages associated with a specified Telegram bot for a given application. This command allows users to remove specific messages by providing their keys.

## Parameters

| Type     | Argument/Flag | Description                                                                              | Required |
| -------- | ------------- | ---------------------------------------------------------------------------------------- | -------- |
| **Args** | `<app-name>`  | **Required**: The name of the application for which to delete messages.                  | Yes      |
| **Args** | `[keys...]`   | **Optional**: The keys of the messages to be deleted. At least one key must be provided. | No       |

## Example

```bash
# Delete messages with keys "command1" and "command2" for the application named "MyApp"
portex bot message del MyApp command1 command2
```

## Success and Failure Messages

- **Success**: If the messages are deleted successfully, you will see the following message:

  - `Bot message(s) deleted successfully`

- **Failure**: If an error occurs during the deletion process, you will see the following message:
  - `Failed to delete bot message(s)`
  - If the application is not bound to a Telegram Bot, the following message will be displayed:
    - `Telegram Application is not bound to a Telegram bot. Please use 'portex bot register <application_name> <bot_token>' to bind a Telegram bot before deleting messages.`
  - If the platform is not Telegram, the following message will be displayed:
    - `Only Telegram Application supports.`

## Notes

- **Platform Support**: The `portex bot message del` command is only supported for applications bound to the Telegram platform.
- **Key Requirement**: At least one message key must be provided for deletion.
- **Error Handling**: Make sure to handle any potential errors during the deletion process to provide appropriate feedback.
