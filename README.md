# Wallet & Expenses

> A comprehensive personal finance and debt management application built with Flutter. Track your income, expenses, and personal debts with robust offline capabilities and automatic cloud synchronization.

[![Flutter](https://img.shields.io/badge/Flutter-3.10%2B-blue.svg)](https://flutter.dev)
[![License](https://img.shields.io/badge/License-Proprietary-red.svg)](#-license)
[![Platform](https://img.shields.io/badge/Platform-Android%20%7C%20iOS%20%7C%20Windows%20%7C%20Linux%20%7C%20macOS-lightgrey.svg)](#-platform-support)

---

## 📥 Download

**[Get the Latest Release (APK)](https://github.com/07-Ansh/Wallet/releases/latest)**

---

## 📸 Graphics

<img src="assets/graphics.jpeg" />

---

## 🚀 Features

### 💰 **Wallet Management**

- **Dual Balance Tracking**: Separate tracking for **Cash** (physical wallet) and **Online** (bank/UPI) transactions
- **Smart Categorization**: Organize income and expenses with customizable categories
- **Transaction History**: Complete audit trail with edit, delete, and filtering capabilities
- **Date Filtering**: View transactions by custom date ranges
- **Quick Actions**: Fast income/expense entry with saved titles for recurring items
- **Real-time Dashboard**: Live overview of your financial health with visual breakdowns

### 🤝 **Debt Manager**

- **People-Centric Design**: Organize debts by contact person
- **Lent & Borrowed**: Clearly distinguish between money you've lent vs. borrowed
- **Two-Way Synchronization**: 
  - Adding a debt automatically creates a corresponding wallet transaction
  - Updating a transaction updates the linked debt record
  - Deleting a debt removes the associated transaction
  - **Never let your balances fall out of sync!**
- **Contact Integration**: Import contacts directly from your phone
- **Status Tracking**: Mark debts as active or settled
- **Communication**: Direct WhatsApp messaging and calling integration
- **Person Profiles**: View complete debt history per person

### ☁️ **Secure Cloud Backup**

- **Automatic Sync**: Data automatically backed up to your personal Google Drive after changes
- **AES-256 Encryption**: All backups are encrypted before upload
- **Silent Recovery**: Automatic data restoration upon sign-in after reinstalling
- **Privacy-First**: Uses restricted `appDataFolder` scope—the app cannot access your other Drive files
- **Retention Policy**: Keeps last 5 backups, automatically deletes older ones
- **Manual Export**: Export encrypted backups to local storage or share via any app
- **Preview Before Restore**: View backup metadata before importing

### 🔒 **Security & Privacy**

- **Biometric Authentication**: Secure app access with Face ID, Fingerprint, or other device biometrics
- **PIN Protection**: 4-digit PIN fallback mechanism
- **Local-First Architecture**: All data stored locally (SQLite) for instant access
- **End-to-End Encryption**: Backups encrypted with AES-256
- **Secure Key Management**: Encryption keys stored in Firebase Firestore + Flutter Secure Storage
- **No Tracking**: Zero analytics or telemetry—your data stays yours

### 🎨 **Customization**

- **Theme Support**: Beautiful Light and Dark modes with Material Design 3
- **Google Fonts**: Premium typography with Outfit font family
- **Custom App Title**: Personalize your app name
- **User Profiles**: Set your profile information
- **Adaptive UI**: Responsive design for all screen sizes

---

## 🏗️ Architecture

### **Data Flow**

```
┌─────────────────┐
│   User Interface│
│   (Screens)     │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ Database Service│ ──────► SQLite (Local)
│   (Business)    │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ Backup Service  │ ──────► Encryption ──────► Google Drive
└─────────────────┘         (AES-256)          (Cloud)
         │
         ▼
┌─────────────────┐
│   Auth Guard    │ ──────► Firebase Auth
└─────────────────┘
```

### **Key Components**

- **Local Database**: SQLite with comprehensive schema for transactions, debts, persons, categories
- **Bi-Directional Sync**: Automatic synchronization between debts and wallet transactions
- **Encryption Layer**: AES-256 encryption for all cloud backups
- **Authentication**: Firebase Auth with Google Sign-In
- **Cloud Storage**: Google Drive API with restricted appDataFolder scope

---

## 🛠️ Tech Stack

### **Core Framework**
- **Flutter** (^3.10.4) - Cross-platform UI framework
- **Dart** - Programming language

### **Database & Storage**
- **SQLite** ([sqflite](https://pub.dev/packages/sqflite)) - Local database
- **sqflite_common_ffi** - Desktop platform support
- **Shared Preferences** - Settings storage
- **Flutter Secure Storage** - Secure key storage
- **Path Provider** - File system access

### **Firebase Services**
- **Firebase Core** - Firebase initialization
- **Firebase Auth** - Google authentication
- **Cloud Firestore** - Encryption key management

### **Google Services**
- **Google Sign-In** - OAuth authentication
- **Google APIs** - Drive API integration
- **Extension Google Sign-In as Googleapis Auth** - Auth bridge

### **Security**
- **Encrypt** - AES-256 encryption
- **Local Auth** - Biometric authentication

### **UI/UX**
- **Google Fonts** - Typography (Outfit font)
- **Lucide Icons** - Modern icon set
- **Flutter Animate** - Micro-interactions
- **Material Design 3** - Design system

### **Utilities**
- **Intl** - Date/number formatting
- **UUID** - Unique ID generation
- **Flutter Contacts** - Contact access
- **Image Picker** - Photo selection
- **File Picker** - File selection
- **Share Plus** - Share functionality
- **PDF & Printing** - PDF generation
- **URL Launcher** - External links
- **Country Picker** - Country selection
- **Package Info Plus** - App version info

---

## 📱 Platform Support

| Platform | Status | Features |
|----------|--------|----------|
| **Android** | ✅ Full Support | All features including biometric auth, contacts |
| **iOS** | ✅ Full Support | All features including Face ID, contacts |
| **Windows** | ✅ Full Support | All features except contacts |
| **Linux** | ✅ Full Support | All features except contacts |
| **macOS** | ✅ Full Support | All features including Touch ID |
| **Web** | ⚠️ Not Supported | Limited compatibility |

---

## 🔐 Security

### **Authentication**
- Firebase Authentication with Google Sign-In
- Secure session management
- Automatic token refresh

### **Data Protection**
- **At Rest**: Local SQLite database storage
- **In Transit**: HTTPS for all network requests
- **Backups**: AES-256 encrypted before uploading to Drive

### **Access Control**
- Biometric authentication (Face ID, Fingerprint)
- 4-digit PIN fallback
- Auto-lock on app backgrounding

### **Key Management**
- Encryption keys stored in Firebase Firestore
- Local key caching with Flutter Secure Storage
- Per-user unique encryption keys

### **Privacy**
- Local-first data storage
- Restricted Drive API scope (appDataFolder only)
- No third-party analytics or tracking
- All backups encrypted end-to-end

---

## 🤝 Contributing

This is a closed-source project. The source code is not publicly available. Only compiled releases are distributed through this repository.

For feature requests or bug reports, please open an issue.

---

## 📄 License

**ALL RIGHTS RESERVED**

Copyright © 2026. All source code, designs, and intellectual property contained in this repository are the exclusive property of the owner. Unauthorized copying, distribution, modification, or use of this software, via any medium, is strictly prohibited.

---

## 📧 Contact

For inquiries, please contact the repository owner.

---

## 🙏 Acknowledgments

- Flutter team for the excellent framework
- Firebase for backend services
- Google for Drive API and authentication
- The open-source community for amazing packages

---

<div align="center">
  <strong>Built with ❤️ using Flutter</strong>
</div>
