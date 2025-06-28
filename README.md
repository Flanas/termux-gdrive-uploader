# Termux Google Drive Uploader

This Bash script helps Termux users on Android upload `.txt` files from any local folder to a designated Google Drive folder using `rclone` and `gupload`. It includes automation via `cron` and handles expired token recovery for `rclone`.

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

## 🚀 Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/YOUR_USERNAME/termux-gdrive-uploader.git
