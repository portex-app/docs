---
icon: table-list
---

# Check Mini-app

```bash
# List applications
portex ls [-i <application-id>] [-n <application-name>] [-p <platform-name>]
```

## Description

The `portex ls` command is used to fetch and display a list of applications. You can filter the list based on the application ID, application name, or platform name. If no flags are provided, it will return all applications.

## Parameters

| Type     | Argument/Flag         | Description                                               | Required |
| -------- | --------------------- | --------------------------------------------------------- | -------- |
| **Flag** | `-i, --appId`         | **Optional**: The application ID to filter the list by.   | No       |
| **Flag** | `-n, --appName`       | **Optional**: The application name to filter the list by. | No       |
| **Flag** | `-p, --platform_name` | **Optional**: The platform name to filter the list by.    | No       |
| **Flag** | `-h, --help`          | **Optional**: Display help information for the command.   | No       |

## Example

```bash
# List all applications
portex ls

# List applications by application ID
portex ls -i app123

# List applications by application name
portex ls -n MyApp

# List applications by platform name
portex ls -p web
```

## Success and Failure Messages

*   **Success**: When the list of applications is successfully fetched, the applications will be displayed in a tabular format, including details such as application ID, name, platform, description, and version.

    **Sample Output**:

| appliaction\_id             | app\_name | platform\_name | description | version |    |    |    |
| --------------------------- | --------- | -------------- | ----------- | ------- | -- | -- | -- |
| last                        | dev       | test           | prod        |         |    |    |    |
| 2vHJYRLPpqL8jEq5J79pse2uPV0 | gameva    | Web            | -           | 17      | 12 | 17 | 17 |

* **Failure**: If no applications are found based on the filters or if an error occurs during the fetching process, you will see the following messages:
  * `No application found, please create an application first`
  * `Get application list error`

## Notes

* **Filtering**: You can filter the list of applications by providing one or more flags:
  * `-i` for the application ID
  * `-n` for the application name
  * `-p` for the platform name (e.g., `web`, `telegram`)
* **Tabular Output**: The applications are displayed in a table with the following columns:
  * **appliaction\_id**: The unique ID of the application.
  * **app\_name**: The name of the application.
  * **platform\_name**: The platform on which the application is deployed (e.g., `web`).
  * **description**: A brief description of the application.
  * **version**: The application version, including its last, development, test, and production versions.
