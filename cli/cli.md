---
icon: square-terminal
---

# CLI

## Portex CLI (beta)

Portex CLI is a command line tool for creating and managing mini-games on multiple platforms.

### Installation

```bash
npm install -g @portex-app/cli
```

### Usage

```bash
portex --help
```

Available Commands:

| command   | description             |
| --------- | ----------------------- |
| `login`   | Login to Portex CLI     |
| `new`     | Create a new mini-game  |
| `ls`      | List all mini-games and get app-id      |
| `deploy`  | Deploy mini-game        |
| `publish` | Publish mini-game       |
| `bot`     | Manage bots in the game |

### Quick Start

> Note: This assumes you installed the CLI tool (npm install -g @portex-app/cli)

#### Login Portex CLI

```bash
# Login to Portex CLI, you can get the login token from email
portex login

# Create a new mini-game
portex new

# Deploy mini-game
portex deploy <app-name> <build-path> [description]

# Publish mini-game, default is dev
portex publish <app-name> <version> [-e dev|test|prod]
```

### Development vs Production

Portex CLI supports development and production environments, when you deploy a mini-game, you can specify the environment.

```bash
portex publish <app-name> <version> -e dev
```

or

```bash
portex publish <app-name> <version> -e prod
```


### How to visit portex mini-game

when you publish a mini-game, you can visit it in the browser.

* production url:
> https://\<app-name\>.portex.app/

* development url:
> https://\<app-name\>.dev.portex.app/

* test url:
> https://\<app-name\>.test.portex.app/

* enter url in portex delivery service:
you must keep `index.html` in the root of your mini-game.

* demo: https://plane.portex.app/


### FAQ: 

* How to get a portex cli access token?

> contact us in telegram. to get a portex cli access token.
><figure><img src="../assets/contact.png" alt="contact us" width="128"></figure>
>
> [https://t.me/televerseadmin](https://t.me/televerseadmin)

