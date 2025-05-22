---
description: >-
  WebApp 是一个允许您创建可在 Telegram WebApp API 中使用的 Web 应用的功能。
icon: mobile-button
---

# Web 应用适配器

## 功能

- 从客户端获取用户信息
- 自定义 Web 应用主题
- 支持客户端传感器（如触觉、加速度计、设备方向、陀螺仪、位置）
- 展开或最小化 Web 应用
- 在客户端浏览器中打开链接

## 示例

```typescript
const portex = new Portex({
	appId: 'your-app-id',
})

await portex.init()

portex.webApp.openLink('https://google.com')
portex.webApp.ready() // 一个通知 Telegram 应用 Mini App 已准备好显示的方法。
portex.webApp.expand() // 一个将 Mini App 展开到最大可用高度的方法。
portex.webApp.close() // 一个关闭 Mini App 的方法。
```

## API 文档

[https://sdk.portex.app/docs/interfaces/core_types.WebApp.html](https://sdk.portex.app/docs/interfaces/core_types.WebApp.html)
