---
icon: arrow-progress
---

# 工作流程

![Portex 工作流程](../assets/workflow.png)

## 1. 部署小游戏进行测试

* 安装 portex cli

```bash
npm install -g @portex-app/cli
```

* 运行 `portex new` 创建新的小游戏
* 运行 `portex deploy` 部署小游戏进行测试

更多详情请查看[使用 CLI](guides/cli.md)

## 2. 在 Telegram 中创建机器人

* 打开 Telegram 并搜索 @BotFather
* 在聊天中开始 /newbot
* 为您的机器人设置名称
* 获取机器人令牌

## 3. 在 Portex 中配置机器人

* 使用 `portex bot` 配置机器人
* 运行 `portex bot register <app-name> <bot-token>` 注册机器人

## 4. 将 Portex SDK 集成到您的小游戏中

* 将 https://sdk.portex.app/portex-sdk.min.js 导入到您的小游戏中
* 您可以运行 `portex ls` 列出所有带有应用 ID 的小游戏
* 使用您的应用 ID 初始化 Portex SDK

```javascript
const portex = new Portex({
  appId: 'your-app-id',
});

const result = await sdk.init();
```

更多详情请查看[Portex SDK](sdk/overview.md)

## 5. 发布您的小游戏

* 运行 `portex publish` 将您的小游戏发布到生产环境
