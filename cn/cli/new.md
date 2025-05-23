---
icon: grid-2-plus
---

# 新建小游戏

```bash
# 发布应用，默认为开发环境
portex publish <app-name> <version> [-e dev|test|prod]
```

## 描述

`portex publish` 命令用于将特定版本的应用发布到指定环境。此命令允许用户将应用部署到不同的环境，如开发、测试或生产环境。如果未指定环境，默认环境为 `dev`。

## 参数

| 类型     | 参数/标志      | 描述                                                                                                              | 是否必需 |
| -------- | ------------- | ------------------------------------------------------------------------------------------------------------------------ | -------- |
| **参数** | `<app-name>`  | **必需**：要发布的应用名称。                                                                    | 是      |
| **参数** | `<version>`   | **必需**：要发布的应用版本。                                                                 | 是      |
| **标志** | `-e, --env`   | **可选**：指定要发布到的环境。可接受的值是 `dev`、`test` 或 `prod`。默认为 `dev`。 | 否       |

## 示例

```bash
# 将名为 "MyApp" 的应用版本 "1" 发布到生产环境
portex publish MyApp 1 -e prod
```

## 交互式输入

如果未提供 `-e` 标志，系统会在执行发布操作之前提示您确认环境。可用选项包括：

* **dev**（开发环境）
* **test**（测试环境）
* **prod**（生产环境）

## 成功和失败消息

* **成功**：如果应用成功发布，您将看到以下消息：
  * `发布应用成功！`
  * 将显示预览 URL，具体取决于环境：
    * **生产环境**：`https://<app-name>.portex.app/`
    * **开发环境**：`https://<app-name>.dev.portex.app/`
    * **测试环境**：`https://<app-name>.test.portex.app/`
* **失败**：如果在发布过程中发生错误，您将看到以下消息：
  * `发布应用失败，请重试`

## 注意事项

* **环境**标志（`-e`）是可选的。如果未提供，默认环境为 `dev`。
* 发布后，将生成预览 URL，您可以使用它访问指定环境中的应用。
* 在尝试发布操作之前，请确保要发布的版本存在。
