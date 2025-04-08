# Login to Portex

```bash
# Login to Portex account
portex login
```

## Description

The `portex login` command is used to authenticate and log in to your Portex account. It prompts you to enter your account credentials (username and password), and then sends the login request to the Portex API. Upon successful login, the authentication token is saved to the local configuration file.

## Parameters

None

## Example

```bash
# Login to Portex account interactively
portex login
```

## Interactive Input

- The system will prompt you to enter your **account** (login name).
- Then, it will prompt you for your **password** (hidden input).
- After successful input, the credentials are sent to the Portex API for authentication.

## Success and Failure Messages

- **Success**: Upon successful login, the system will display the following success message:

  ```
  Initialization completed. Congratulations! 🎉 🎉 🎉
  ```

- **Failure**: If the login fails, you will receive an error message:

  ```
  Initialization failed, please try again
  ```

## Notes

- **Token Storage**: After a successful login, the authentication token is saved to the local configuration file, allowing you to authenticate for subsequent requests without needing to log in again.

- **Configuration Directory**: If the configuration directory does not exist, it will be created automatically before storing the authentication token.
