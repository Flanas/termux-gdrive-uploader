# Termux Google Drive Uploader

This Bash script helps Termux users on Android upload files from any local folder in an android device to a designated Google Drive folder using `rclone` and `gupload`. It includes automation via `cron` and handles expired token recovery for `rclone`.

## Considerations

rclone will explicitely solicit access to your google account, so be sure to have a supported browser (Chrome, Firefox, Brave and even Edge will wor)
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
