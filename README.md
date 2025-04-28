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

LifeInDrive/
├── app/
│   ├── navigation/
│   │   ├── AppNavigator.tsx        # Main Stack Navigator (Card-based)
│   │   ├── TabNavigator.tsx        # Bottom Tabs (Home, Notes, Tasks, etc.)
│   │   └── RootNavigation.tsx      # Helper for navigating outside screens
│
├── screens/
│   ├── HomeScreen.tsx              # Dashboard linking to cards
│   ├── TodaysTasksScreen.tsx       # "Today's Tasks" Card
│   ├── NotesScreen.tsx             # Notes list & editor
│   ├── QuickCaptureScreen.tsx      # Quick add notes, tasks, images
│   ├── MyDayScreen.tsx             # Premium AI daily planner
│   ├── MyPlannerScreen.tsx         # Premium journaling screen
│   ├── VoiceMemosScreen.tsx        # Voice recording & playback
│   ├── SettingsScreen.tsx          # Theme, preferences, account
│   ├── PremiumScreen.tsx           # Upgrade/subscribe flow
│   └── Auth/
│       ├── LoginScreen.tsx         # Login
│       └── RegisterScreen.tsx      # Registration
│
├── components/
│   ├── CardLink.tsx                # Reusable card button
│   ├── NoteCard.tsx                # Mini note previews
│   ├── TaskItem.tsx                # Task checklist UI
│   ├── AudioPlayer.tsx             # Voice memo playback UI
│   ├── UpgradeBanner.tsx           # Promote Premium plan
│
├── constants/
│   ├── colors.ts                   # Color palettes
│   ├── fonts.ts                    # Typography setup
│   └── strings.ts                  # Static text labels
│
├── context/
│   └── ThemeContext.tsx            # Light/Dark mode toggler
│
├── hooks/
│   ├── useAuth.ts                  # Supabase authentication hook
│   ├── useTasks.ts                 # Fetch/manage tasks
│   └── useNotes.ts                 # Fetch/manage notes
│
├── store/
│   └── useAppStore.ts               # Zustand global state (theme, auth, user prefs)
│
├── lib/
│   ├── supabase.ts                 # Supabase client config
│   ├── aiEngine.ts                 # ONNX Runtime AI loader for My Day
│   ├── ocrEngine.ts                # OCR utilities (for image notes)
│   ├── iap.ts                      # In-app purchases (react-native-iap)
│   └── analytics.ts                # PostHog event tracking
│
├── utils/
│   ├── dateUtils.ts                # Date formatting, reminders
│   ├── storageUtils.ts             # AsyncStorage wrappers
│   └── navigationUtils.ts          # Navigate outside stack helpers
│
├── assets/
│   ├── images/                     # Logos, icons
│   ├── fonts/                      # Custom fonts (if needed)
│   └── audio/                      # Sample audio prompts
│
├── .env                            # Environment variables
├── App.tsx                         # Entry point → RootNavigator
├── app.json                        # Expo config
├── babel.config.js                 # Babel config (NativeWind, Reanimated, etc.)
├── eas.json                        # EAS Build profiles
├── metro.config.js                 # Asset handling (optional)
└── README.md                       # Project documentation

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
