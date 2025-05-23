---
icon: upload
---

# 部署小游戏

```bash
# 部署小游戏
portex deploy <app-name> <build-path> [description]
```

## 描述

`portex deploy` 命令用于从指定的构建路径上传应用包。此命令允许用户通过提供应用名称和构建路径来部署应用。它将应用文件压缩为 zip 格式，计算 MD5 校验和，获取用于上传的预签名 URL，最后上传压缩文件。

上传成功后，命令将显示应用的最后部署版本，用户可以使用 `portex publish` 命令发布新版本。

## 参数

| 参数       | 描述                                                               | 是否必需 |
| --------------- | ------------------------------------------------------------------------- | -------- |
| `<app-name>`    | 要部署的应用名称。此参数是必需的。        | 是      |
| `<build-path>`  | 应用构建文件的路径。此参数也是必需的。 | 是      |
| `[description]` | 部署的可选描述。                               | 否       |

## 示例

```bash
# 部署名为 "MyApp" 的应用，构建路径为 "./build"
portex deploy MyApp ./build "这是一个测试应用的描述"
```

## 命令工作流程

| 步骤 | 名称                     | 描述                                                                                                                                     |
| ---- | ------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| 1    | 压缩应用     | 将指定构建路径下的应用文件压缩为 zip 文件。                                                           |
| 2    | 计算 MD5 校验和   | 计算压缩 zip 文件的 MD5 校验和，以确保上传过程中的数据完整性。                                                  |
| 3    | 获取预签名 URL        | 从 API 获取预签名 URL 以安全地上传文件。                                                                             |
| 4    | 上传文件              | 将压缩的 zip 文件上传到预签名 URL。                                                                                           |
| 5    | 显示应用版本 | 显示应用的最后部署版本。用户然后可以使用 `portex publish` 命令和下一个版本号进行发布。 |

## 成功和失败消息

*   **成功**：部署成功后，系统将显示：

    ```
    部署成功
    应用最后版本：1
    您可以使用 'portex publish MyApp 1 [-e dev|test|prod]' 命令发布应用
    ```
*   **失败**：如果部署过程在任何阶段失败，您将看到错误消息，例如：

    ```
    部署失败
    ```

## 注意事项

* **压缩**：应用文件夹在上传前被压缩为 zip 文件。
* **旧文件清理**：系统将自动清理旧的部署文件，仅保留最近的四个文件。
* **进度条**：文件上传过程中将显示进度条，以指示上传进度。
* **应用最后版本**：部署后，将显示最后部署的版本，您可以使用 `portex publish` 命令和下一个版本号来发布应用。

## 附加信息

* **查看版本信息**：您可以使用 `portex ls` 命令获取版本信息并检查版本发布状态。
* **发布版本**：要将版本发布到指定环境，您可以使用 `portex publish` 命令和版本号。
