# Deploy Mini-App

```bash
# Deploy a mini-app
portex deploy <app-name> <build-path> [description]
```

## Description

The `portex deploy` command is used to upload an application package from the specified build path. This command allows users to deploy applications by providing the application name and build path. It compresses the application files into a zip format, calculates the MD5 checksum, retrieves a presigned URL for uploading, and finally uploads the compressed file.

After a successful upload, the command will display the application’s last deployed version, and users can use the `portex publish` command to publish the new version.

## Parameters

| Parameter       | Description                                                               | Required |
| --------------- | ------------------------------------------------------------------------- | -------- |
| `<app-name>`    | The name of the application to deploy. This parameter is required.        | Yes      |
| `<build-path>`  | The path to the application build files. This parameter is also required. | Yes      |
| `[description]` | An optional description for the deployment.                               | No       |

## Example

```bash
# Deploy an application named "MyApp" with the build path "./build"
portex deploy MyApp ./build "This is a description for a test application"
```

## Command Workflow

| Step | Name                     | Description                                                                                                                                     |
| ---- | ------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| 1    | Compress Application     | Compresses the application files located at the specified build path into a zip file.                                                           |
| 2    | Calculate MD5 Checksum   | Calculates the MD5 checksum of the compressed zip file to ensure data integrity during upload.                                                  |
| 3    | Get Presigned URL        | Retrieves a presigned URL from the API to upload the file securely.                                                                             |
| 4    | Upload File              | Uploads the compressed zip file to the presigned URL.                                                                                           |
| 5    | Show Application Version | Displays the last deployed version of the application. Users can then use the `portex publish` command with the next version number to publish. |

## Success and Failure Messages

- **Success**: After a successful deployment, the system will display:

  ```
  Deploy success
  Application Last Version: 1
  You can use 'portex publish MyApp 1 [-e dev|test|prod]' command to publish application
  ```

- **Failure**: If the deployment process fails at any stage, you will see an error message such as:

  ```
  Deploy failed
  ```

## Notes

- **Compression**: The application folder is compressed into a zip file before being uploaded.
- **Old Files Cleanup**: The system will automatically clear out old deployment files, retaining only the four most recent ones.
- **Progress Bar**: A progress bar will be shown during the file upload to indicate the upload progress.
- **Application Last Version**: After deployment, the last deployed version is displayed, and you can use the `portex publish` command with the next version number to publish the application.

## Additional Information

- **View Version Information**: You can use the `portex ls` command to retrieve version information and check the status of version releases.
- **Publish Version**: To publish a version to a specified environment, you can use the `portex publish` command with the version number.
