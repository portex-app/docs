---
description: >-
  Portex SDK is a development kit for creating mini-games on telegram, web and
  other platforms.
icon: boxes-packing
---

# Overview

## Portex SDK (beta)

### Install

* inline `https://sdk.portex.app/portex-sdk.min.js` to your mini-game
* or build from source code

```bash
git clone https://github.com/portex-app/portex-sdk.git
cd portex-sdk

pnpm install
pnpm build
```

### Usage

> Note: this is a beta version, you can only use it in telegram. get app-id from [Portex CLI](../cli/overview.md)

* initialize Portex SDK with your app-id

```javascript
const portex = new Portex({
  appId: 'your-app-id',
});

try {
  const result = await portex.init();

  if (result.status === 'ok') {
    // init success
    // get user info
    consle.log(sdk.webApp.initDataUnsafe);
  } else {
    // init failed
  }
} catch (error) {
  console.error(error);
}

```

* SDK Demo: https://t.me/portex\_app\_bot?startapp

### SDK Features

* [Social Invite](sdk/social.md)
* [Payment](sdk/payment.md)
* [Webapp Adapter](sdk/webapp.md)
* ads (coming soon)
* leaderboard (coming soon)
* game save (coming soon)

### API Reference

* [Portex SDK API](https://sdk.portex.app/docs/index.html)

### Source

{% @github-files/github-code-block url="https://github.com/portex-app/portex-sdk" %}
