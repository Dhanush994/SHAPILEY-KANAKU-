# 📱 APK Generation Guide for Shapiley Kanaku

## 🎯 Overview
This guide provides step-by-step instructions to convert the Shapiley Kanaku web application into an Android APK for office installation.

## 🛠️ Method 1: Capacitor (Recommended)

### Prerequisites
- Node.js installed
- Android Studio installed
- Java Development Kit (JDK) 8 or higher

### Step 1: Install Capacitor
```bash
npm install @capacitor/core @capacitor/cli
npm install @capacitor/android
```

### Step 2: Initialize Capacitor
```bash
npx cap init "Shapiley Kanaku" "com.shapiley.kanaku"
```

### Step 3: Build the Web App
```bash
npm run build
```

### Step 4: Add Android Platform
```bash
npx cap add android
```

### Step 5: Copy Web Assets
```bash
npx cap copy android
```

### Step 6: Open in Android Studio
```bash
npx cap open android
```

### Step 7: Build APK in Android Studio
1. In Android Studio, go to **Build** → **Build Bundle(s) / APK(s)** → **Build APK(s)**
2. Wait for the build to complete
3. APK will be generated in `android/app/build/outputs/apk/debug/`

## 🛠️ Method 2: Cordova (Alternative)

### Prerequisites
- Node.js installed
- Cordova CLI installed globally

### Step 1: Install Cordova
```bash
npm install -g cordova
```

### Step 2: Create Cordova Project
```bash
cordova create shapiley-kanaku com.shapiley.kanaku "Shapiley Kanaku"
cd shapiley-kanaku
```

### Step 3: Add Android Platform
```bash
cordova platform add android
```

### Step 4: Copy Built Files
1. Build your web app: `npm run build`
2. Copy contents of `dist/` folder to `www/` folder in Cordova project

### Step 5: Build APK
```bash
cordova build android
```

## 🛠️ Method 3: PWA to APK (Easiest)

### Using PWA Builder
1. Visit [PWABuilder.com](https://www.pwabuilder.com/)
2. Enter your deployed web app URL
3. Click "Generate Package"
4. Select Android and download APK

### Using Bubblewrap
```bash
npm install -g @bubblewrap/cli
bubblewrap init --manifest https://yourapp.com/manifest.json
bubblewrap build
```

## 📋 Required Files for APK Generation

### Essential Files to Include:
```
📁 Complete Project Structure
├── 📄 package.json (with all dependencies)
├── 📄 vite.config.ts
├── 📄 tailwind.config.js
├── 📄 tsconfig.json
├── 📁 src/ (entire source code)
├── 📁 public/ (including LOGO.jpeg)
└── 📄 index.html
```

### Additional Configuration Files:
```
📄 capacitor.config.ts (for Capacitor method)
📄 config.xml (for Cordova method)
📄 manifest.json (for PWA method)
```

## ⚙️ Capacitor Configuration

Create `capacitor.config.ts`:
```typescript
import { CapacitorConfig } from '@capacitor/cli';

const config: CapacitorConfig = {
  appId: 'com.shapiley.kanaku',
  appName: 'Shapiley Kanaku',
  webDir: 'dist',
  bundledWebRuntime: false,
  android: {
    allowMixedContent: true,
    captureInput: true
  }
};

export default config;
```

## 📱 PWA Manifest Configuration

Create `public/manifest.json`:
```json
{
  "name": "Shapiley Kanaku",
  "short_name": "Shapiley",
  "description": "Daily Financial Tracker",
  "start_url": "/",
  "display": "standalone",
  "background_color": "#ffffff",
  "theme_color": "#3b82f6",
  "icons": [
    {
      "src": "/LOGO.jpeg",
      "sizes": "192x192",
      "type": "image/jpeg"
    }
  ]
}
```

## 🔧 Build Commands Summary

### For Development:
```bash
npm install
npm run dev
```

### For Production Build:
```bash
npm run build
npm run preview
```

### For APK Generation (Capacitor):
```bash
npm run build
npx cap copy android
npx cap open android
# Then build APK in Android Studio
```

## 📦 Final APK Location

After successful build, your APK will be located at:
- **Capacitor**: `android/app/build/outputs/apk/debug/app-debug.apk`
- **Cordova**: `platforms/android/app/build/outputs/apk/debug/app-debug.apk`

## 🚀 Installation Instructions for Office Use

1. **Enable Unknown Sources** on Android devices
2. **Transfer APK** to device via USB, email, or cloud storage
3. **Install APK** by tapping on the file
4. **Launch** Shapiley Kanaku from app drawer
5. **Enter any 4-digit PIN** to access the system

## ⚠️ Important Notes

- APK will be in **debug mode** (for production, use release build)
- App will work **offline** with local storage
- **Data backup** should be done regularly via PDF reports
- For **production deployment**, consider code signing and Play Store distribution

---
**Generated**: ${new Date().toLocaleString()}