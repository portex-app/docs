---
description: >-
  Portex SDK 是一个用于在 Telegram、Web 和其他平台上创建小游戏的开发工具包。
icon: boxes-packing
---

# 概述

## Portex SDK（测试版）

### 安装

- 将 `https://sdk.portex.app/portex-sdk.min.js` 内联到您的小游戏中
- 或从源代码构建

```bash
git clone https://github.com/portex-app/portex-sdk.git
cd portex-sdk

pnpm install
pnpm build
```

### 使用方法

> 注意：这是测试版本，您只能在 Telegram 中使用它。从 [Portex CLI](../cli/overview.md) 获取应用 ID。

- 使用您的应用 ID 初始化 Portex SDK

```javascript
const portex = new Portex({
	appId: 'your-app-id',
})

try {
	const result = await portex.init()

	if (result.status === 'ok') {
		// 初始化成功
		// 获取用户信息
		consle.log(sdk.webApp.initDataUnsafe)
	} else {
		// 初始化失败
	}
} catch (error) {
	console.error(error)
}
```

- SDK 演示：https://t.me/portex\_app\_bot?startapp

### SDK 功能

- [社交邀请](sdk/social.md)
- [支付](sdk/payment.md)
- [Webapp 适配器](sdk/webapp.md)
- 广告（即将推出）
- 排行榜（即将推出）
- 游戏存档（即将推出）

### API 参考

- [Portex SDK API](https://sdk.portex.app/docs/index.html)

### 源代码

{% @github-files/github-code-block url="https://github.com/portex-app/portex-sdk" %}
