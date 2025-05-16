# List Telegram Bot Messages

```bash
# Get the list of messages for a Telegram bot
portex bot message ls <app-name>
```

## Description

The `portex bot message ls` command is used to retrieve the list of messages associated with a specified Telegram bot for a given application. This command allows users to view all the messages that have been saved for the bot.

## Parameters

| Type     | Argument/Flag | Description                                                           | Required |
| -------- | ------------- | --------------------------------------------------------------------- | -------- |
| **Args** | `<app-name>`  | **Required**: The name of the application for which to list messages. | Yes      |

## Example

```bash
# List messages for the application named "MyApp"
portex bot message ls MyApp
```

## Success and Failure Messages

- **Success**: If the messages are retrieved successfully, you will see a table output displaying the message keys and their corresponding content:

  ```
  +----------------+--------------------------+
  | message_key    | message_content          |
  +----------------+--------------------------+
  | command1       | Hello                    |
  | command2       | Another message          |
  +----------------+--------------------------+
  ```

- **Failure**: If an error occurs during the retrieval process, you will see the following message:
  - `get bot message failed`
  - If the application is not bound to a Telegram Bot, the following message will be displayed:
    - `Telegram Application is not bound to a Telegram bot. Please use 'portex bot register <application_name> <bot_token>' to bind a Telegram bot before getting the bot message list.`
  - If no messages are found, the following message will be displayed:
    - `No message found`
  - If the platform is not Telegram, the following message will be displayed:
    - `Only Telegram Application supports.`

## Notes

- **Platform Support**: The `portex bot message ls` command is only supported for applications bound to the Telegram platform.
- **Error Handling**: Make sure to handle any potential errors during the retrieval process to provide appropriate feedback.
