# Portex CLI

Portex CLI is a command line tool for creating and managing mini-games on multiple platforms.

## Installation

```bash
npm install -g @portex-app/portex-cli
```

## Usage

```bash
portex --help
```

Available Commands:

| command            | description                     |
|-----------------|--------------------------|
| `login`  | Login to Portex CLI       |
| `new`    | Create a new mini-game     |
| `ls`     | List all mini-games         |
| `deploy`  | Deploy mini-game             |
| `publish` | Publish mini-game             |
| `bot`    | Manage bots in the game       |


## Quick Start
> Note: This assumes you installed the CLI tool (npm install -g portex-cli)

### Login Portex CLI

```bash
# Login to Portex CLI, you can get the login token from email
portex login
```

### Create a new mini-game

```bash
# Create a new mini-game
portex new
```

### List all mini-games

```bash
# List all mini-games
portex ls
```

### Deploy mini-game

```bash
# Deploy mini-game
portex deploy <app-name> <build-path> [description]
```

### Publish mini-game

```bash
# Publish mini-game, default is dev
portex publish <app-name> <version> [-e dev|test|prod]
```

## How to visit


## Development vs Production

Portex CLI supports development and production environments, when you deploy a mini-game, you can specify the environment.

```bash
portex publish <app-name> <version> -e dev
```

or 

```bash
portex publish <app-name> <version> -e prod
```
