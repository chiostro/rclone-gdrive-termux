# Rclone Setup on Termux with Google Drive

This guide explains how to install and configure **Rclone** on Termux to connect your Android device with **Google Drive**.

---

## Prerequisites
- An Android device with **Termux** installed  
- A **Google account** with access to Google Drive  
- Internet connection  

---

## Installation

Install Rclone by running:
```bash
pkg install rclone
```
Configuration
Start the configuration process with:
```bash
rclone config
```



Steps to configure:
Create a new remote

Type n (for new remote) and press Enter.

Enter a name for your remote (e.g., gdrive or mygdrive) and press Enter.

You will see a list of storage types. Select Google Drive (usually option 12, but check the list).

Confirm the remote name and storage type.

Set credentials

client_id and client_secret: For most users, just press Enter to leave them blank (default values will be used).

scope: Choose the desired access level. If you want full access to your Google Drive, select the option that allows reading and writing files (drive).

root_folder: Leave empty or set a specific folder ID if you want the remote to only manage a particular folder.

service_account_file: Press Enter to leave blank, unless you are using an advanced service account configuration.

Authorize access

You will be asked to authorize the remote. Type y and press Enter.

Termux will display a URL. Copy and open this URL in a browser on your computer or device.

Log in with your Google account and grant Rclone access.

You will receive an authorization code. Copy this code.

Complete setup

Return to Termux and paste the authorization code.

Press Enter to finish the configuration.

Finally, you will be asked whether to confirm the remote configuration. Type q (quit) to exit or y (yes) to confirm.

## Usage
Now your Google Drive remote is configured and ready.
You can start using it with Rclone commands, for example:

bash
Copia codice
### List files on your remote Google Drive

```bash
rclone ls gdrive:
```

### Copy a file from Termux to Google Drive
```bash
rclone copy /sdcard/myfile.txt gdrive:
```

### Sync a folder from Termux to Google Drive
```bash
rclone sync /sdcard/Documents gdrive:/DocumentsBackup
```

Notes
Replace gdrive with the name you chose for your remote.

Ensure you have a stable internet connection for syncing.

For advanced setups (like service accounts or shared drives), check the official Rclone documentation.

## License
This guide is provided under the MIT License.

