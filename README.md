# Windows Server 2016 Evaluation to Standard Edition Conversion Process

## Objective
This document provides the procedure for converting a Windows Server 2016 Evaluation edition to the Standard edition. Follow the steps below to ensure a smooth and successful conversion process.

## Prerequisites
- **Windows Server 2016 Evaluation Edition** installed on the server.
- **Windows Server 2016 Standard Product Key** (KMS Key): `WC2BQ-8NRM3-FDDYY-2BFGV-KHKQY`
- Administrator privileges on the server.

## Steps to Convert Windows Server 2016 Evaluation to Standard Edition

### 1. Open Command Prompt as Administrator
- Click the **Start** menu.
- Type **cmd** in the search bar.
- Right-click on **Command Prompt** and select **Run as administrator** to open an elevated Command Prompt window.

### 2. Set Edition to Windows Server 2016 Standard
- In the elevated Command Prompt, enter the following command:
  ```bash
  dism /online /set-edition:ServerStandard /productkey:WC2BQ-8NRM3-FDDYY-2BFGV-KHKQY /accepteula
  ```

### 3. Reboot the Server
- The system will request a restart. **Reboot the server twice** to complete the edition change.
- Ensure the server restarts fully before proceeding to the next step.

### 4. Verify Edition Change
- After the server restarts, verify that the conversion to the Standard edition was successful.
- Open **Command Prompt** and type the following:
  ```bash
  winver
  ```

### 5. Install the KMS Key
- In the elevated Command Prompt, type the following command to install the KMS product key for Windows Server 2016 Standard:
  ```bash
  slmgr /ipk WC2BQ-8NRM3-FDDYY-2BFGV-KHKQY
  ```

  ```bash
  slmgr /skms kms8.msguides.com
  ```

### 6. Activate Windows Server
- To activate the installed product key, enter the following command:
  ```bash
  slmgr /ato
  ```

### 7. Confirm Activation
- After activation, verify the status by running the following command:
  ```bash
  slmgr /dli
  ```

## Conclusion
Once the above steps are completed, your server will be successfully converted from the Evaluation edition to the Standard edition, with the proper KMS key applied and activated.

## Additional Notes
- Ensure all server-related applications and services are functioning properly after the conversion.
- If you encounter any activation errors, verify that the server is connected to the KMS server and try activating again.
- Always back up critical data before making significant system changes.
