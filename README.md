# Termux Google Drive Uploader

This Bash script helps Termux users on Android upload files from any local folder in an android device to a designated Google Drive folder using `rclone` and `gupload`. It includes automation via `cron` and handles expired token recovery for `rclone`.

## Considerations

rclone will explicitely solicit access to your google account, so be sure to have a supported browser (Chrome, Firefox, Brave and even Edge will work)
If you can access the storage in termux run the following command 'termux-setup-storage' this will enable changing directory inside termux's terminal/cmd (however you want to call it). us cd command to move around
To run the .sh file just run 'bash thenameyousavedthefilewith.sh'
LF may have been replaced by CRLF meaning that if the file presents issues when running you may have to get into visual studio code, change to LF in the bottom right.
'termux-wake-lock' can also be runned in termux to disable battery optimization in termux

## 🔧 Features

- Google Drive integration via `rclone` and `gupload`
- Automatic token refresh for expired rclone configs
- Background sync using Termux cron (`cronie`)
- Full setup automation: packages, permissions, configs
- Optional system monitoring

## 📦 Requirements

- Termux
- Internet access
- A Google Cloud project with a valid **Client ID** and **Client Secret**
- Your desired folder path in Android
- Automate uploads!

## 🚀 Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/Flanas/termux-gdrive-uploader.git

## 🔐 Better Practice: Use a .env File
For security and flexibility, you should store your credentials in a .env file and source it inside the script.

Example .env file:
env
Copy
Edit
REMOTE_URL="https://your-webdav-server.com"
REMOTE_USER="your-username"
REMOTE_PASS="your-password"
At the top of your script, add:

bash
Copy
Edit
source $HOME/.env
This keeps sensitive data out of the main script and version control.

## 🌐 About Rclone Authorization
If you're configuring rclone to use a remote like Google Drive:

Rclone will open a browser window to request access to your Google account.

Make sure you have a supported browser installed on Android:

Chrome

Firefox

Brave

Edge

This step is only required if you're using Google-based remotes, not WebDAV.

## ⚠️ Windows Line Ending Warning
If you wrote or downloaded the .sh file using Windows and it won't run properly in Termux, it may be using CRLF line endings. To fix this:

Open the file in Visual Studio Code

In the bottom-right corner, click CRLF

Change it to LF

Save the file and try running it again in Termux

## 🔒 Preventing Job Termination
To avoid Android killing background jobs, you can enable a wake-lock:

bash
Copy
Edit
termux-wake-lock
This disables battery optimization and keeps Termux running during background tasks.

## 📁 Directory Structure Example
Uploaded files will appear in your WebDAV server as:

php-template
Copy
Edit
/<MAIN_FOLDER>/<SUB_FOLDER>/<filename>.txt
This helps you organize logs by project, customer, or device ID.

## 💡 Navigating Storage in Termux
Use cd to change directories (e.g., cd /storage/emulated/0/Download)

Use ls to view contents

Run the .sh file by typing:

bash
Copy
Edit
bash WebDAV-OnPremise-upload.sh
