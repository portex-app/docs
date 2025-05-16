---
description: >-
  portex.invite is a feature that allows users to invite their friends to join
  the game.
icon: users
---

# Invite Friends

## API Documentation

* open dialog to invite friends to join the game

```typescript
invite(options: InviteOptions): Promise<InviteResult>
```

* get invite url, don't open dialog

```typescript
getInviteUrl(options: InviteOptions): Promise<InviteResult>
```

* get invite payload, get/set invite payload to server, with a limit of over 64 characters

```typescript
getInvitePayload(key: string): Promise<InvitePayloadResult>
```

* get start param

```typescript
getStartParam(): string
```

## Interface

```typescript
interface InviteOptions {
    expire: number; // expiration time, seconds
    text?: string; // invite text in dialog
    payload?: string; // save to server, over 64 characters
    start_param?: string; // invite url with start_param, over 64 characters
}

interface InviteResult {
    invite_url: string; // invite url
    key?: string; // payload key
}

interface InvitePayloadResult {
    payload: string; // payload
}
```

## Example

```javascript
// Initialize SDK
const portex = new Portex({
  appId: 'your-app-id'
});

// Initialize and verify user
await portex.init();

// Invite friends
const inviteResult = await portex.invite({
  expire: 3600, // Expiration time (seconds)
  text: 'Come play with me!',
  start_param: 'custom-data'
}); 
```

## Notes

* `payload` & `start_param` use one of them, not both
