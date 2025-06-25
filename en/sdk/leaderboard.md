---
description: >-
  portex.leaderboard provides leaderboard capabilities for games or
  applications.
icon: horse
---

# Leaderboard

## API Documentation

* Submit user score

```typescript
updateUserLeaderboardScore(options:LeaderboardUpdateUserScoreOptions):Promise<void>

```

* Get topN leaderboard data

```typescript
getLeaderboardTopN(options: LeaderboardTopNOptions): Promise<LeaderboardTopNResult>

```

* Get user's leaderboard rank information

```typescript
 getLeaderboardRank(options: LeaderboardRankOptions): Promise<LeaderboardRankResult>
```

## Interface

```typescript
interface LeaderboardUpdateUserScoreOptions {
	/** Sort direction, asc=0 desc=1, only effective for first data upload */
	direction: number
	/** Extra data */
	extra?: string
	/** Leaderboard name */
	leaderboard_name: string
	/** User ID */
	user_id: string
	/** User score, the key field for sorting */
	score: number
}

interface LeaderboardTopNOptions {
	/** Leaderboard name */
	leaderboard_name: string
	/** Get leaderboard length, maximum support 1000 */
	top_n: number
}

interface LeaderboardTopNUser {
	/** User ID */
	user_id: string
	/** User score, the key field for sorting */
	score: number
	/** Extra data submitted by updateUserLeaderboardScore function */
	extra: string
}

interface LeaderboardTopNResult {
	/** Information of users on the leaderboard */
	leaderboard_users: Array<LeaderboardTopNUser>
}

interface LeaderboardRankOptions {
	/** Leaderboard name */
	leaderboard_name: string
	/** User ID */
	user_id: string
}

interface LeaderboardRankResult {
	/** User rank */
	rank: number
	/** Extra data submitted by updateUserLeaderboardScore function */
	extra: string
}
```

## Example

```javascript
// Initialize SDK
const portex = new Portex({
	appId: 'your-app-id',
})

// Initialize and verify user
await portex.init()

// Submit user score
await portex.updateUserLeaderboardScore({
	leaderboard_name: 'your-leaderboard',
	direction: 0,
	extra: '{"username":"userName","avatar":"avatar"}',
	user_id: 'user-id',
	score: 100,
})

// Get user's leaderboard rank
const userLeaderboardRank = await portex.getLeaderboardRank({
	leaderboard_name: 'your-leaderboard',
	user_id: 'user-id',
})

// Get leaderboard ranking data
const leaderboardTopN = await portex.getLeaderboardTopN({
	leaderboard_name: 'your-leaderboard',
	/** Maximum 1000, will throw exception if exceeded */
	top_n: 1000,
})
```

## Notes

* `top_n` has a maximum limit of 1000, exceeding this will throw an exception
* The `userLeaderboardRank` function will return an exception if the rank exceeds 10000
