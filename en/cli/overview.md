---
icon: square-terminal
---

# Use CLI

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

| command   | description                        |
| --------- | ---------------------------------- |
| `login`   | Login to Portex CLI                |
| `new`     | Create a new mini-game             |
| `ls`      | List all mini-games and get app-id |
| `deploy`  | Deploy mini-game                   |
| `publish` | Publish mini-game                  |
| `bot`     | Manage bots in the game            |

### Quick Start

> Note: This assumes you installed the CLI tool (npm install -g @portex-app/cli)

#### Login to Portex CLI

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

Portex CLI supports development and production environments. When you deploy a mini-game, you can specify the environment.

```bash
portex publish <app-name> <version> -e dev
```

or

```bash
portex publish <app-name> <version> -e prod
```

### How to Visit Portex Mini-Game

When you publish a mini-game, you can visit it in the browser.

- Production URL:

  > https://\<app-name>.portex.app/

- Development URL:

  > https://\<app-name>.dev.portex.app/

- Test URL:

  > https://\<app-name>.test.portex.app/

- Enter URL in Portex delivery service:\
  You must keep `index.html` in the root of your mini-app.
- Demo: https://plane.portex.app/

### Source

{% @github-files/github-code-block url="https://github.com/portex-app/portex-cli" %}

### FAQ

- How to get a Portex CLI access token?

> Contact us on Telegram to get a Portex CLI access token.
>
> <img src="../assets/contact.png" alt="" data-size="original">
>
> [https://t.me/televerseadmin](https://t.me/televerseadmin)
