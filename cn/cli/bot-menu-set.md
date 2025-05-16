# 设置 Telegram 菜单按钮

```bash
# 为 Telegram 机器人设置菜单按钮
portex bot menu set <app-name> <menu-url>
```

## 描述

`portex bot menu set` 命令用于为指定应用的 Telegram 机器人设置菜单按钮。此命令允许用户更新机器人的菜单按钮 URL。

## 参数

| 类型     | 参数/标志      | 描述                                                                 | 是否必需 |
| -------- | ------------- | --------------------------------------------------------------------------- | -------- |
| **参数** | `<app-name>`  | **必需**：要设置菜单按钮的应用名称。 | 是      |
| **参数** | `<menu-url>`  | **必需**：菜单按钮将链接到的 URL。                    | 是      |

## 示例

```bash
# 为名为 "MyApp" 的应用设置菜单按钮，URL 为 "http://example.com/menu"
portex bot menu set MyApp http://example.com/menu
```

## 成功和失败消息

- **成功**：如果菜单按钮更新成功，您将看到以下消息：

  - `菜单按钮更新成功`

- **失败**：如果在更新过程中发生错误，您将看到以下消息：
  - `更新菜单按钮失败`
  - 如果应用未绑定 Telegram 机器人，将显示以下消息：
    - `Telegram 应用未绑定 Telegram 机器人。请使用 'portex bot register <application_name> <bot_token>' 在设置菜单之前绑定 Telegram 机器人。`
  - 如果平台不是 Telegram，将显示以下消息：
    - `仅支持 Telegram 应用。`

## 注意事项

- **平台支持**：`portex bot menu set` 命令仅支持绑定到 Telegram 平台的应用。
- **错误处理**：确保在更新过程中处理任何潜在错误，以提供适当的反馈。
