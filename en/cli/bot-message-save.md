# Save Telegram Bot Messages

```bash
# Save Telegram Bot messages
portex bot message save <app-name> <messages>
```

## Description

The `portex bot message save` command is used to save Telegram Bot messages associated with a specified application. This command allows users to format messages as JSON and save them to the application bound to the Telegram Bot.

## Parameters

| Type     | Argument/Flag | Description                                                           | Required |
| -------- | ------------- | --------------------------------------------------------------------- | -------- |
| **Args** | `<app-name>`  | **Required**: The name of the application for which to save messages. | Yes      |
| **Args** | `<messages>`  | **Required**: The bot messages represented in JSON format.            | Yes      |

## Messages Structure

The `messages` parameter should be a JSON object that conforms to the `BotMessages` interface. Below is the structure of the `messages`:

```json
{
	"command1": {
		"text": "Hello",
		"buttons": [
			[
				{
					"text": "Button1",
					"url": "http://example.com"
				}
			]
		],
		"description": "This is a command description",
		"keyboard": {
			"buttons": [
				[
					{
						"text": "Keyboard Button",
						"web_app": {
							"url": "http://example.com/app"
						}
					}
				]
			],
			"input_field_placeholder": "Type your message here...",
			"is_persistent": true,
			"one_time": false,
			"resize": true,
			"selective": false
		},
		"parse_mode": "HTML"
	}
}
```

### Explanation of the Structure

- **command1**: Represents a command that the bot can respond to.
- **text**: The message text that will be displayed to the user.
- **buttons**: An array of button arrays. Each button can have:
  - **text**: The label of the button.
  - **url**: A link that will be opened when the button is clicked (for public chats).
  - **web_app**: An object containing a `url` that will be opened in a web app (for private chats).
- **description**: A description of the command that will be displayed in the command list (only in private chat).
- **keyboard**: An object representing the keyboard layout:
  - **buttons**: An array of button arrays for the keyboard.
  - **input_field_placeholder**: Placeholder text for the input field.
  - **is_persistent**: A boolean indicating whether the keyboard is persistent.
  - **one_time**: A boolean indicating whether the keyboard is one-time use.
  - **resize**: A boolean indicating whether the keyboard should be resized.
  - **selective**: A boolean indicating whether the keyboard should be selectively displayed.
- **parse_mode**: The message content parsing mode, which can be "HTML", "Markdown", or "MarkdownV2".

## Example

```bash
# Save bot messages related to the application named "MyApp"
portex bot message save MyApp '{"command1": {"text": "Hello", "buttons": [[{"text": "Button1", "url": "http://example.com"}]], "description": "This is a command description", "keyboard": {"buttons": [[{"text": "Keyboard Button", "web_app": {"url": "http://example.com/app"}}]], "input_field_placeholder": "Type your message here...", "is_persistent": true, "one_time": false, "resize": true, "selective": false}, "parse_mode": "HTML"}}'
```

## Success and Failure Messages

- **Success**: If the messages are saved successfully, you will see the following message:

  - `Save bot messages successfully`

- **Failure**: If an error occurs during the saving process, you will see the following message:
  - `Save bot messages failed`
  - If the application is not bound to a Telegram Bot, the following message will be displayed:
    - `Telegram Application is not bound to a Telegram bot. Please use 'portex bot register <application_name> <bot_token>' to bind a Telegram bot before saving bot messages.`
  - If the platform is not Telegram, the following message will be displayed:
    - `Only Telegram Application supports.`

## Notes

- **Platform Support**: The `portex bot message save` command is only supported for applications bound to the Telegram platform.
- **Message Format**: Ensure that the provided message format conforms to the `BotMessages` interface definition.
- **Error Handling**: Make sure to handle any potential errors during the saving process to provide appropriate feedback.
