---
description: >-
  portex.invite 是一个允许用户邀请好友加入游戏的功能。
icon: users
---

# 邀请好友

## API 文档

- 打开对话框邀请好友加入游戏

```typescript
invite(options: InviteOptions): Promise<InviteResult>
```

- 获取邀请链接，不打开对话框

```typescript
getInviteUrl(options: InviteOptions): Promise<InviteResult>
```

- 获取邀请负载，从服务器获取/设置邀请负载，限制超过 64 个字符

```typescript
getInvitePayload(key: string): Promise<InvitePayloadResult>
```

- 获取启动参数

```typescript
getStartParam(): string
```

## 接口

```typescript
interface InviteOptions {
	expire: number // 过期时间，单位秒
	text?: string // 对话框中的邀请文本
	payload?: string // 保存到服务器，超过 64 个字符
	start_param?: string // 带有 start_param 的邀请链接，超过 64 个字符
}

interface InviteResult {
	invite_url: string // 邀请链接
	key?: string // 负载键
}

interface InvitePayloadResult {
	payload: string // 负载
}
```

## 示例

```javascript
// 初始化 SDK
const portex = new Portex({
	appId: 'your-app-id',
})

// 初始化并验证用户
await portex.init()

// 邀请好友
const inviteResult = await portex.invite({
	expire: 3600, // 过期时间（秒）
	text: '来和我一起玩吧！',
	start_param: 'custom-data',
})
```

## 注意事项

- `payload` 和 `start_param` 只能使用其中一个，不能同时使用
