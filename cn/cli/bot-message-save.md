# 保存 Telegram 机器人消息

```bash
# 保存 Telegram 机器人消息
portex bot message save <app-name> <messages>
```

## 描述

`portex bot message save` 命令用于保存与指定应用关联的 Telegram 机器人消息。此命令允许用户将消息格式化为 JSON 并保存到绑定到 Telegram 机器人的应用中。

## 参数

| 类型     | 参数/标志      | 描述                                                           | 是否必需 |
| -------- | ------------- | --------------------------------------------------------------------- | -------- |
| **参数** | `<app-name>`  | **必需**：要保存消息的应用名称。 | 是      |
| **参数** | `<messages>`  | **必需**：以 JSON 格式表示的机器人消息。            | 是      |

## 消息结构

`messages` 参数应该是一个符合 `BotMessages` 接口的 JSON 对象。以下是 `messages` 的结构：

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

### 结构说明

- **command1**：表示机器人可以响应的命令。
- **text**：将显示给用户的消息文本。
- **buttons**：按钮数组的数组。每个按钮可以包含：
  - **text**：按钮的标签。
  - **url**：点击按钮时将打开的链接（用于公共聊天）。
  - **web_app**：包含将在 Web 应用中打开的 `url` 的对象（用于私人聊天）。
- **description**：命令的描述，将显示在命令列表中（仅在私人聊天中）。
- **keyboard**：表示键盘布局的对象：
  - **buttons**：键盘按钮数组的数组。
  - **input_field_placeholder**：输入字段的占位符文本。
  - **is_persistent**：指示键盘是否持久的布尔值。
  - **one_time**：指示键盘是否一次性使用的布尔值。
  - **resize**：指示键盘是否应调整大小的布尔值。
  - **selective**：指示键盘是否应选择性显示的布尔值。
- **parse_mode**：消息内容解析模式，可以是 "HTML"、"Markdown" 或 "MarkdownV2"。

## 示例

```bash
# 保存与名为 "MyApp" 的应用相关的机器人消息
portex bot message save MyApp '{"command1": {"text": "Hello", "buttons": [[{"text": "Button1", "url": "http://example.com"}]], "description": "This is a command description", "keyboard": {"buttons": [[{"text": "Keyboard Button", "web_app": {"url": "http://example.com/app"}}]], "input_field_placeholder": "Type your message here...", "is_persistent": true, "one_time": false, "resize": true, "selective": false}, "parse_mode": "HTML"}}'
```

## 成功和失败消息

- **成功**：如果消息保存成功，您将看到以下消息：

  - `保存机器人消息成功`

- **失败**：如果在保存过程中发生错误，您将看到以下消息：
  - `保存机器人消息失败`
  - 如果应用未绑定 Telegram 机器人，将显示以下消息：
    - `Telegram 应用未绑定 Telegram 机器人。请使用 'portex bot register <application_name> <bot_token>' 在保存机器人消息之前绑定 Telegram 机器人。`
  - 如果平台不是 Telegram，将显示以下消息：
    - `仅支持 Telegram 应用。`

## 注意事项

- **平台支持**：`portex bot message save` 命令仅支持绑定到 Telegram 平台的应用。
- **消息格式**：确保提供的消息格式符合 `BotMessages` 接口定义。
- **错误处理**：确保在保存过程中处理任何潜在错误，以提供适当的反馈。
