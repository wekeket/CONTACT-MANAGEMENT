# Contact Manager (Android)

An offline-first Android contact manager built with React Native and Expo.

## Offline operation

The app stores contacts and contact groups in a local SQLite database on the Android device. The app does not need an internet connection to create, view, edit, delete, search, filter, favorite, or group contacts.

Backups are exported as JSON files to the device's local cache and can be restored by selecting a backup file. Backup files are only shared or imported when the user initiates the action.

There is no cloud account, remote database, or contact synchronization service in this project. Removing the app or clearing its app data may erase the local database, so export backups regularly.

Calling, texting, and emailing use the phone's Android apps and may require cellular service, Wi-Fi, or an email account. These are optional shortcuts; contact management itself works offline.

## Features

- Create, view, edit, and delete contacts
- Contact groups and group membership
- Search contacts by name, phone, or email
- Favorites and alphabetical/recent sorting
- Contact details with call, SMS, and email shortcuts
- JSON backup export and restore
- Persistent local SQLite database

## Expo SDK

This project targets Expo SDK 58. Keep Expo, React, React Native, and Expo native modules aligned. After pulling dependency changes, run `npx expo install --fix` and `npx expo-doctor` before starting Metro.

The local SQLite database is named `contacts.db`. The SDK upgrade does not require deleting or recreating it. Keep the app slug and Android package identifier unchanged, do not clear app data, and export a JSON backup from Settings before upgrading as a precaution.

## Requirements

- Node.js LTS
- npm
- Expo Go (for development) or an Android APK build (for standalone use)

## Run in development

```bash
npm install
npx expo start
```

Expo Go / Metro is used to load the development JavaScript bundle. This is a development workflow and is not the same as installing a standalone offline app.

## Build an installable Android APK

Configure EAS and build an APK:

```bash
npm install -g eas-cli
eas login
eas build:configure
eas build --platform android --profile preview
```

Install the resulting APK on the Android phone. Once installed, the app's contact management features and SQLite database work without Wi-Fi or mobile data. An internet connection is needed for the cloud build process and downloading the APK, not for normal local contact management.

## Data and privacy

Contacts are stored locally in SQLite on the device. This starter does not upload contacts to a server. Export a JSON backup before uninstalling the app or clearing its storage.
