---
icon: square-terminal
---

# 使用 CLI

## Portex CLI（测试版）

Portex CLI 是一个命令行工具，用于在多个平台上创建和管理小游戏。

### 安装

```bash
npm install -g @portex-app/cli
```

### 使用方法

```bash
portex --help
```

可用命令：

| 命令      | 描述                           |
| --------- | ------------------------------ |
| `login`   | 登录到 Portex CLI              |
| `new`     | 创建新的小游戏                 |
| `ls`      | 列出所有小游戏并获取应用 ID    |
| `deploy`  | 部署小游戏                     |
| `publish` | 发布小游戏                     |
| `bot`     | 管理游戏中的机器人             |

### 快速开始

> 注意：这假设您已经安装了 CLI 工具（npm install -g @portex-app/cli）

#### 登录到 Portex CLI

```bash
# 登录到 Portex CLI，您可以从邮件中获取登录令牌
portex login

# 创建新的小游戏
portex new

# 部署小游戏
portex deploy <app-name> <build-path> [description]

# 发布小游戏，默认为开发环境
portex publish <app-name> <version> [-e dev|test|prod]
```

### 开发环境与生产环境

Portex CLI 支持开发和生产环境。当您部署小游戏时，可以指定环境。

```bash
portex publish <app-name> <version> -e dev
```

或

```bash
portex publish <app-name> <version> -e prod
```

### 如何访问 Portex 小游戏

当您发布小游戏后，可以在浏览器中访问它。

- 生产环境 URL：

  > https://\<app-name>.portex.app/

- 开发环境 URL：

  > https://\<app-name>.dev.portex.app/

- 测试环境 URL：

  > https://\<app-name>.test.portex.app/

- 在 Portex 分发服务中输入 URL：\
  您必须将 `index.html` 放在小应用的根目录中。
- 演示：https://plane.portex.app/

### 源代码

{% @github-files/github-code-block url="https://github.com/portex-app/portex-cli" %}

### 常见问题

- 如何获取 Portex CLI 访问令牌？

> 通过 Telegram 联系我们获取 Portex CLI 访问令牌。
>
> <img src="../assets/contact.png" alt="" data-size="original">
>
> [https://t.me/televerseadmin](https://t.me/televerseadmin)
