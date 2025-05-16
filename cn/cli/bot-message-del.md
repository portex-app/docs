# 删除 Telegram 机器人消息

```bash
# 删除 Telegram 机器人的消息
portex bot message del <app-name> [keys...]
```

## 描述

`portex bot message del` 命令用于删除指定应用的 Telegram 机器人的一个或多个消息。此命令允许用户通过提供消息的键来删除特定消息。

## 参数

| 类型     | 参数/标志      | 描述                                                                              | 是否必需 |
| -------- | ------------- | ---------------------------------------------------------------------------------------- | -------- |
| **参数** | `<app-name>`  | **必需**：要删除消息的应用名称。                  | 是      |
| **参数** | `[keys...]`   | **可选**：要删除的消息的键。必须提供至少一个键。 | 否       |

## 示例

```bash
# 删除名为 "MyApp" 的应用中键为 "command1" 和 "command2" 的消息
portex bot message del MyApp command1 command2
```

## 成功和失败消息

- **成功**：如果消息删除成功，您将看到以下消息：

  - `机器人消息删除成功`

- **失败**：如果在删除过程中发生错误，您将看到以下消息：
  - `删除机器人消息失败`
  - 如果应用未绑定 Telegram 机器人，将显示以下消息：
    - `Telegram 应用未绑定 Telegram 机器人。请使用 'portex bot register <application_name> <bot_token>' 在删除消息之前绑定 Telegram 机器人。`
  - 如果平台不是 Telegram，将显示以下消息：
    - `仅支持 Telegram 应用。`

## 注意事项

- **平台支持**：`portex bot message del` 命令仅支持绑定到 Telegram 平台的应用。
- **键要求**：必须提供至少一个消息键才能删除。
- **错误处理**：确保在删除过程中处理任何潜在错误，以提供适当的反馈。
