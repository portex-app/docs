# 登录到 Portex

```bash
# 登录到 Portex 账户
portex login
```

## 描述

`portex login` 命令用于验证并登录到您的 Portex 账户。它会提示您输入账户凭据（用户名和密码），然后将登录请求发送到 Portex API。登录成功后，认证令牌将保存到本地配置文件中。

## 参数

无

## 示例

```bash
# 交互式登录到 Portex 账户
portex login
```

## 交互式输入

- 系统会提示您输入**账户**（登录名）。
- 然后，它会提示您输入**密码**（隐藏输入）。
- 成功输入后，凭据将发送到 Portex API 进行认证。

## 成功和失败消息

- **成功**：登录成功后，系统将显示以下成功消息：

  ```
  初始化完成。恭喜！🎉 🎉 🎉
  ```

- **失败**：如果登录失败，您将收到错误消息：

  ```
  初始化失败，请重试
  ```

## 注意事项

- **令牌存储**：登录成功后，认证令牌将保存到本地配置文件中，允许您在后续请求中进行认证，无需再次登录。

- **配置目录**：如果配置目录不存在，系统将在存储认证令牌之前自动创建它。
