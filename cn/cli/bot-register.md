# 绑定 Telegram 机器人

```bash
# 注册 Telegram 机器人
portex bot register <app-name> <bot-token>
```

## 描述

`portex register` 命令用于为指定应用注册 Telegram 机器人。此命令允许用户通过提供应用名称和 tg 机器人令牌将 Telegram 机器人绑定到他们的应用。它会与 Telegram 验证并尝试注册机器人，处理过程中可能出现的任何错误。

## 参数

* `<app-name>`：要部署的应用名称。此参数是必需的。
* `<bot-token>`：Telegram 机器人的令牌。此参数也是必需的。

**提示**：要获取您的机器人令牌，您需要使用 Telegram 上的 [BotFather](https://t.me/botfather) 创建一个新机器人。请按照以下步骤操作：

1. 打开 Telegram 并搜索 "BotFather"。
2. 与 BotFather 开始聊天，使用命令 `/newbot` 创建新机器人。
3. 按照提示为您的机器人设置名称和用户名。
4. 创建完成后，BotFather 将为您提供一个令牌。复制此令牌并在命令中使用它。

## 示例

```bash
# 为名为 "MyApp" 的应用注册 Telegram 机器人，机器人令牌为 "123456:ABC-DEF1234ghIkl-zyx57W2P0"
portex register MyApp '123456:ABC-DEF1234ghIkl-zyx57W2P0'
```

## 注意事项

* 如果平台不是 'Telegram'，命令将抛出错误，表明只有 Telegram 平台支持此命令。
* 如果绑定失败，将显示适当的错误消息。
* **解绑机器人**：不支持；当前版本不支持解绑 Telegram 机器人。
