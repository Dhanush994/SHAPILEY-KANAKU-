# Shapiley Kanaku - Complete Backup Package

## 📋 Project Overview
**Shapiley Kanaku** is a daily financial tracking system designed for point-of-sale operations. This backup contains the complete source code and deployment instructions.

## 🏗️ Project Structure
```
shapiley-kanaku/
├── public/
│   ├── LOGO.jpeg                 # Company logo
│   └── vite.svg                  # Vite favicon
├── src/
│   ├── components/
│   │   ├── Dashboard.tsx         # Main dashboard interface
│   │   └── LoginScreen.tsx       # PIN-based authentication
│   ├── data/
│   │   └── expenseCategories.ts  # Expense and suspense categories
│   ├── types/
│   │   └── index.ts              # TypeScript type definitions
│   ├── utils/
│   │   ├── dateUtils.ts          # Date formatting utilities
│   │   ├── reportGenerator.ts    # PDF report generation
│   │   └── storage.ts            # Local storage management
│   ├── App.tsx                   # Main application component
│   ├── index.css                 # Global styles
│   └── main.tsx                  # Application entry point
├── index.html                    # HTML template
├── package.json                  # Dependencies and scripts
├── tailwind.config.js            # Tailwind CSS configuration
├── postcss.config.js             # PostCSS configuration
├── vite.config.ts                # Vite build configuration
└── tsconfig.json                 # TypeScript configuration
```

## 🚀 Features
- **PIN-based Authentication** - Secure 4-digit PIN login
- **Daily Financial Tracking** - Cash sales, card sales, expenses
- **BOH (Back of House) Management** - Separate tracking for BOH received
- **Expense Categorization** - Predefined categories for expenses and suspense items
- **PDF Report Generation** - Automated daily reports with detailed breakdowns
- **Data Persistence** - Local storage for offline functionality
- **Responsive Design** - Works on desktop, tablet, and mobile devices
- **Professional UI** - Light blue theme with modern design

## 💰 Financial Calculations
- **Total Sales** = Cash Sales + Card Sales (BOH NOT included)
- **Closing Balance** = Opening Balance + Cash Sales + BOH Received - Total Deductions
- **Total Deductions** = Cash Expenses + Suspense Items

## 🛠️ Installation Instructions

### Prerequisites
- Node.js (v16 or higher)
- npm or yarn package manager

### Setup Steps
1. Extract the backup files to your desired directory
2. Navigate to the project directory
3. Install dependencies: `npm install`
4. Start development server: `npm run dev`
5. Build for production: `npm run build`

## 📱 Mobile/APK Deployment Options

### Option 1: Progressive Web App (PWA)
- Add PWA manifest and service worker
- Users can "Add to Home Screen" on mobile devices
- Works offline with cached data

### Option 2: Capacitor (Recommended for APK)
- Install Capacitor: `npm install @capacitor/core @capacitor/cli`
- Add Android platform: `npx cap add android`
- Build and sync: `npm run build && npx cap sync`
- Open in Android Studio: `npx cap open android`

### Option 3: Cordova
- Install Cordova: `npm install -g cordova`
- Create Cordova project and copy dist files
- Build APK: `cordova build android`

## 🔧 Configuration
- **Logo**: Replace `/public/LOGO.jpeg` with your company logo
- **Colors**: Modify `tailwind.config.js` for theme customization
- **Categories**: Update `src/data/expenseCategories.ts` for expense types
- **Authentication**: Currently accepts any 4-digit PIN (modify for production)

## 📊 Data Storage
- Uses browser localStorage for data persistence
- Data format: JSON with daily entries per user
- Automatic backup through localStorage
- Export functionality via PDF reports

## 🔒 Security Notes
- PIN authentication is basic (enhance for production)
- Data stored locally in browser
- No server-side validation (add for production use)
- Consider encryption for sensitive financial data

## 📞 Support
For technical support or customization requests, refer to the development team.

---
**Generated**: ${new Date().toLocaleString()}
**Version**: 1.0.0
**License**: Proprietary