# Contact Manager (Android)

An offline-first Android contact manager built with React Native and Expo.

## Features
- Create, view, edit, and delete contacts
- Contact groups and group membership
- Search contacts by name, phone, or email
- Favorites and alphabetical sorting
- Contact details with call, SMS, and email shortcuts
- JSON backup export and restore
- Persistent local SQLite database

## Requirements
- Node.js LTS
- npm
- Expo Go (Android) or Android Studio emulator

## Run locally

```bash
npm install
npx expo start
```

Scan the QR code with Expo Go, or press `a` to open an Android emulator.

## Build an APK

```bash
npm install -g eas-cli
eas login
eas build:configure
eas build --platform android --profile preview
```

The `preview` profile in `eas.json` creates an installable APK.

## Data and privacy
Contacts are stored locally in SQLite on the device. Backup files are JSON and are only exported or imported when the user initiates the action. This starter does not upload contacts to a server.
