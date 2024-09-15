# Task_1_CICD

## GitHub Actions Workflow

This GitHub Actions workflow manages and reviews GitHub commits, updates edge devices with unique credentials, and verifies device status post-update.

### Managing and Reviewing GitHub Commits

The workflow uses the following steps to manage and review GitHub commits:

*   **Trigger workflow on push**: The `on: push` directive in the YAML file specifies that this workflow will run on every push to the main branch.
*   **Enforce code reviews**: Implement Pull Request (PR) workflows to enforce code reviews and automated checks before merging changes into the production branch.
*   **Review and approve changes**: Review and approve changes before they are merged into the production branch.

### Managing Different Credentials for Each Edge Device

The workflow uses the following steps to manage different credentials for each edge device:

*   **Update CSV file**: The workflow includes a step that updates the CSV file with the device ID, device key, primary key, secondary key, and IoT Hub host name.
*   **Add multiple entries**: Add multiple entries for different edge devices in the same CSV file, with each entry having its unique credentials.

### Verifying Device Status Post-Update and Receiving Reports

The workflow uses the following steps to verify device status post-update and receive reports from them:

*   **Update device twin**: The `az iot hub device-identity update` command updates the device twin with the specified firmware version.
*   **Verify device status**: The `azure/iot-hub@v1` action is used to verify the device status, ensuring that the update was successful.
*   **Receive reports**: The `receive-reports` command is used to receive reports from the device, allowing you to monitor and review the device's reported properties.
