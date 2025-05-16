---
icon: plane-departure
---

# Publish Mini-app

```bash
# Publish an application, default is dev
portex publish <app-name> <version> [-e dev|test|prod]
```

#### Description

The `portex publish` command is used to publish a specific version of an application to a specified environment. This command allows users to deploy their applications to different environments such as development, testing, or production. If the environment is not specified, the default environment is `dev`.

#### Parameters

| Type     | Argument/Flag | Description                                                                                                              | Required |
| -------- | ------------- | ------------------------------------------------------------------------------------------------------------------------ | -------- |
| **Args** | `<app-name>`  | **Required**: The name of the application to publish.                                                                    | Yes      |
| **Args** | `<version>`   | **Required**: The version of the application to publish.                                                                 | Yes      |
| **Flag** | `-e, --env`   | **Optional**: Specifies the environment to publish to. Acceptable values are `dev`, `test`, or `prod`. Default is `dev`. | No       |

#### Example

```bash
# Publish an application named "MyApp" with version "1" to the production environment
portex publish MyApp 1 -e prod
```

#### Interactive Input

If the `-e` flag is not provided, you will be prompted to confirm the environment before proceeding with the publish action. The available options are:

* **dev** (Development Environment)
* **test** (Test Environment)
* **prod** (Production Environment)

#### Success and Failure Messages

* **Success**: If the application is successfully published, you will see the following message:
  * `Publish application success!`
  * A preview URL will be shown, depending on the environment:
    * **Production**: `https://<app-name>.portex.app/`
    * **Development**: `https://<app-name>.dev.portex.app/`
    * **Test**: `https://<app-name>.test.portex.app/`
* **Failure**: If an error occurs during the publishing process, you will see the following message:
  * `Publish application failed, please try again`

#### Notes

* The **environment** flag (`-e`) is optional. If not provided, the default environment is `dev`.
* After publishing, a preview URL will be generated, which you can use to access the application in the specified environment.
* Ensure that the version you are trying to publish exists before attempting the publish action.
