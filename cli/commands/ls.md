# List Applications

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

- **Success**: When the list of applications is successfully fetched, the applications will be displayed in a tabular format, including details such as application ID, name, platform, description, and version.

  **Sample Output**:

<table border>
  <thead >
    <tr>
      <th rowspan="2">appliaction_id</th>
      <th rowspan="2">app_name</th>
      <th rowspan="2">platform_name</th>
      <th rowspan="2">description</th>
      <th colspan="4">version</th>
    </tr>
    <tr>
      <th>last</th>
      <th>dev</th>
      <th>test</th>
      <th>prod</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>2vHJYRLPpqL8jEq5J79pse2uPV0</td>
      <td>gameva</td>
      <td>Web</td>
      <td>-</td>
      <td>17</td>
      <td>12</td>
      <td>17</td>
      <td>17</td>
    </tr>
  </tbody>
</table>

- **Failure**: If no applications are found based on the filters or if an error occurs during the fetching process, you will see the following messages:
  - `No application found, please create an application first`
  - `Get application list error`

## Notes

- **Filtering**: You can filter the list of applications by providing one or more flags:
  - `-i` for the application ID
  - `-n` for the application name
  - `-p` for the platform name (e.g., `web`, `telegram`)
- **Tabular Output**: The applications are displayed in a table with the following columns:
  - **appliaction_id**: The unique ID of the application.
  - **app_name**: The name of the application.
  - **platform_name**: The platform on which the application is deployed (e.g., `web`).
  - **description**: A brief description of the application.
  - **version**: The application version, including its last, development, test, and production versions.
