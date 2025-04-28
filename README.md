# LifeInDrive

[![Platform](https://img.shields.io/badge/platform-iOS%20%7C%20Android-blue)](https://expo.dev)
[![License: MIT](https://img.shields.io/badge/license-MIT-green)](LICENSE)

**Author:** [botbuilders-dee](https://github.com/botbuilders-dee)

## 📱 Overview
**LifeInDrive** is a cross-platform productivity mobile app inspired by Google Keep. Built using **React Native with Expo** and **Expo Router**, the app enables users to plan their day, take notes, track tasks, and collaborate—augmented by AI and designed with an intuitive UI/UX experience.

---

## 🔧 Tech Stack
- **Framework**: React Native + Expo
- **Routing**: Expo Router (file-based navigation)
- **State Management**: Zustand
- **Backend/Auth/Sync**: Supabase
- **Local AI**: ONNX Runtime for My Day suggestions
- **Audio Recording & Playback**: expo-av
- **Voice Transcription**: Post-recording via offline ML model
- **OCR**: Google ML Kit (image text extraction)
- **Styling**: NativeWind (Tailwind CSS for React Native)
- **Theming**: Light/Dark mode via `tailwind.config.js` and system preference
- **Monetization**: `react-native-iap`

---

## ⚙️ Installation

### Prerequisites
- **Node.js** >= 14.x (recommend 18.x)
- **Expo CLI** (install globally):
  ```bash
  npm install -g expo-cli
  ```
- **EAS CLI** (for building custom dev-client):
  ```bash
  npm install -g eas-cli
  ```

### Setup
```bash
git clone https://github.com/botbuilders-dee/lifeindrive.git
cd lifeindrive
yarn install
```

### Dev Client Build (for native modules like expo-dev-client)
```bash
expo install expo-dev-client
expo prebuild
# Then build Dev Client
EAS build --profile development --platform android
# or
EAS build --profile development --platform ios
```

### Running the App
```bash
yarn start          # Launch Expo Dev Tools
yarn run android    # Run via dev-client (Android)
yarn run ios        # Run via dev-client (iOS)
```

---

## 📁 Project Structure
```bash
app/
├── _layout.tsx        # Root Stack layout
├── index.tsx          # Home Screen
├── todays-tasks.tsx   # Card: Today's Tasks
├── notes.tsx          # Card: Notes
├── quick-capture.tsx  # Card: Quick Capture
components/
├── CardLink.tsx       # Reusable card link component
lib/
├── supabase/          # Auth and Sync logic
├── storage/           # Local Storage utils
state/
├── useAppStore.ts     # Zustand store
```

---

## 🧩 Features
- Card-based navigation UI with smooth transitions
- Offline-first data access (Notes, Tasks)
- AI-generated "My Day" suggestions via ONNX runtime
- Voice memo recording and transcription
- Image note creation via OCR
- Collaboration-ready architecture with Supabase
- Light/Dark Theme auto-switching
- In-app Purchases for premium features

---

## 📜 License

This project is licensed under the [MIT License](LICENSE).

---

## 🔗 Repository

[LifeInDrive GitHub Repo](https://github.com/botbuilders-dee/lifeindrive)
