---
description: >-
  WebApp is a feature that allows you to create a web app that can be used in
  Telegram WebApp API.
icon: mobile-button
---

# Webapp Adapter

## Features

* get user info from client
* customize webapp theme
* support client sensors (like Haptic,Accelerometer, DeviceOrientation, Gyroscope,location)
* expand or minimize webapp
* open link in client browser

## Example

```typescript
const portex = new Portex({
    appId: 'your-app-id',
});

await portex.init();


portex.webApp.openLink('https://google.com');
portex.webApp.ready(); //A method that informs the Telegram app that the Mini App is ready to be displayed.
portex.webApp.expand();//A method that expands the Mini App to the maximum available height.
portex.webApp.close();//A method that closes the Mini App.
```

## API Documentation

https://sdk.portex.app/docs/interfaces/core\_types.WebApp.html
