---
description: >-
  portex.leaderboard 为游戏或者应用提供排行榜能力
  icon:ranking-star
---

# 排行榜

## API 文档

- 提交用户分数

```typescript
updateUserLeaderboardScore(options:LeaderboardUpdateUserScoreOptions):Promise<void>

```

- 获取 topN 排行榜数据

```typescript
getLeaderboardTopN(options: LeaderboardTopNOptions): Promise<LeaderboardTopNResult>

```

- 获取用户的排行榜排名信息

```typescript
 getLeaderboardRank(options: LeaderboardRankOptions): Promise<LeaderboardRankResult>
```

## 接口

```typescript
interface LeaderboardUpdateUserScoreOptions {
	/** 排序方式，asc=0 desc=1,仅第一次上传数据有效 */
	direction: number
	/** 额外数据 */
	extra?: string
	/** 排行榜名称 */
	leaderboard_name: string
	/** 用户ID */
	user_id: string
	/** 用户分数，排序关键的字段 */
	score: number
}

interface LeaderboardTopNOptions {
	/** 排行榜名称 */
	leaderboard_name: string
	/** 获取排行榜长度，最大支持1000 */
	top_n: number
}

interface LeaderboardTopNUser {
	/** 用户ID */
	user_id: string
	/** 用户分数，排序关键的字段 */
	score: number
	/** updateUserLeaderboardScore函数提交的额外数据 */
	extra: string
}

interface LeaderboardTopNResult {
	/** 上榜用户的信息 */
	leaderboard_users: Array<LeaderboardTopNUser>
}

interface LeaderboardRankOptions {
	/** 排行榜名称 */
	leaderboard_name: string
	/** 用户ID */
	user_id: string
}

interface LeaderboardRankResult {
	/** 用户排名 */
	rank: number
	/** updateUserLeaderboardScore函数提交的额外数据 */
	extra: string
}
```

## 示例

```javascript
// 初始化 SDK
const portex = new Portex({
    appId:"your-app-id"
})

// 初始化并验证用户
await portex.init();

// 提交用户分数
await portex portex.updateUserLeaderboardScore({
    leaderboard_name: 'your-leaderboard',
	direction: 0,
	extra: '{"username":"userName","avatar":"avatar"}',
	user_id: 'user-id',
	score: 100,
})

// 获取用户的排行榜排名
const userLeaderboardRank = await portex.getLeaderboardRank({
    leaderboard_name: 'your-leaderboard',
    user_id: 'user-id',
})

// 获取排行榜的排名数据
const leaderboardTopN = await portex.getLeaderboardTopN({
    leaderboard_name: 'your-leaderboard',
    /** 最大1000，超出会抛出异常 */
    top_n:1000,
})

```

## 注意事项

- `top_n` 最大上限是 1000 超出会抛出异常
- 函数`userLeaderboardRank` 获取用户排行，超出 10000 会返回异常
