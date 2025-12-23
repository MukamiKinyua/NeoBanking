# NeoBanking - Modern Banking Application

A comprehensive Android banking application built with Java, featuring modern UI/UX, AI-powered financial advice, transaction management, and complete KYC onboarding.

## Features

### Authentication & Security
- **Email/Password Login** with validation
- **Registration** with full form validation
- **Change Password** with security checks
- **Change PIN** (4-digit) functionality
- **Biometric Authentication** support
- **Secure Storage** using encrypted SharedPreferences
- **Session Management** with logout functionality

## User Onboarding
- **8-Page KYC Process** for new users
- Comprehensive information collection:
  - Personal Information (Name, DOB, SSN, Nationality)
  - Contact & Address Details
  - Financial Information & Employment
  - **Document Uploads** (ID, Address Proof, Income Proof)
  - **Selfie Capture** for verification
  - Account Preferences
  - Security Questions
  - **Digital Signature** capture
- Tab navigation with progress tracking
- Page-by-page validation
- Image upload from camera/gallery

### Transaction Management
- **27 Pre-loaded Dummy Transactions**
- Transaction categories:
  - Food & Dining ($450)
  - Transportation ($300)
  - Entertainment ($200)
  - Shopping ($150)
  - Bills & Utilities ($400)
  - Healthcare ($100)
- Income tracking ($4,300 total)
- Expense tracking ($1,600 total)
- Categorized transaction list
- Search and filter functionality
- Beautiful card-based UI

### Budget & Analytics
- **Interactive Pie Chart** - Spending by category
- **Interactive Bar Chart** - Monthly spending trends
- Real-time data visualization using MPAndroidChart
- Click-to-view detailed amounts
- Toast notifications on interactions
- Color-coded categories

### AI Financial Chatbot
- Smart financial advisor
- Context-aware responses
- Topics covered:
  - Budgeting (50/30/20 rule)
  - Saving strategies
  - Debt management
  - Income growth tips
  - Emergency funds
  - Investment guidance
- Interactive chat interface
- Chat history with timestamps

### Settings & Profile
- **Edit Profile** page with user details
- **Settings** page with:
  - App preferences (Notifications, Biometric, SMS Alerts)
  - Security options
  - Change Password page
  - Change PIN page
- User information display
- Logout with confirmation dialog

### UI/UX Features
- **Material Design 3** components
- Bottom navigation (5 tabs)
- Smooth fragment transitions
- **Toast notifications** for every action
- Error handling with user-friendly messages
- Progress indicators
- Card-based layouts
- Responsive design
- Professional color scheme

## Architecture

### Tech Stack
- **Language:** Java
- **Min SDK:** 24 (Android 7.0)
- **Target SDK:** 34 (Android 14)
- **Build System:** Gradle

### Key Libraries
```gradle
// Material Design
implementation 'com.google.android.material:material:1.11.0'

// Charts
implementation 'com.github.PhilJay:MPAndroidChart:v3.1.0'

// AndroidX
implementation 'androidx.appcompat:appcompat:1.6.1'
implementation 'androidx.constraintlayout:constraintlayout:2.1.4'
implementation 'androidx.recyclerview:recyclerview:1.3.2'
implementation 'androidx.cardview:cardview:1.0.0'
implementation 'androidx.viewpager2:viewpager2:1.0.0'

// Security
implementation 'androidx.security:security-crypto:1.1.0-alpha06'

// Biometric
implementation 'androidx.biometric:biometric:1.2.0-alpha05'
```

### Project Structure
```
com.glorymukami.neobanking/
├── models/
│   └── Transaction.java
├── ui/
│   ├── auth/
│   │   └── AuthActivity.java
│   ├── main/
│   │   └── MainActivity.java
│   ├── splash/
│   │   └── SplashActivity.java
│   ├── onboarding/
│   │   ├── OnboardingActivity.java
│   │   ├── OnboardingPagerAdapter.java
│   │   └── OnboardingPageFragment.java
│   ├── home/
│   │   └── HomeFragment.java
│   ├── transactions/
│   │   ├── TransactionsFragment.java
│   │   └── TransactionsAdapter.java
│   ├── budget/
│   │   └── BudgetFragment.java
│   ├── chatbot/
│   │   ├── ChatbotFragment.java
│   │   ├── ChatAdapter.java
│   │   └── ChatMessage.java
│   ├── profile/
│   │   ├── ProfileFragment.java
│   │   └── EditProfileActivity.java
│   └── settings/
│       ├── SettingsActivity.java
│       ├── ChangePasswordActivity.java
│       └── ChangePinActivity.java
└── utils/
    ├── SecureStorage.java
    ├── DummyData.java
    └── BiometricHelper.java
```


## Getting Started
### Prerequisites
- Android Studio Hedgehog (2023.1.1) or later
- JDK 11 or higher
- Android SDK 34
- Gradle 8.0+

### Installation
1. **Clone or Download** the project
   ```bash
   git clone https://github.com/yourusername/neobanking.git
   ```

2. **Open in Android Studio**
   - File → Open → Select the `NeoBanking` folder

3. **Sync Gradle**
   - Wait for Gradle sync to complete
   - Resolve any dependency issues

4. **Build the Project**
   ```
   Build → Clean Project
   Build → Rebuild Project
   ```

5. **Run the App**
   - Connect an Android device or start an emulator
   - Click Run or press Shift+F10

### First Run Setup
**Demo Credentials:**
- Email: `admin@neobanking.com`
- Password: `password123`

**Or Register:**
1. Click "Don't have an account? Register"
2. Fill in registration form
3. Complete 8-page onboarding
4. Start using the app!


## User Guide

### Registration Flow
```
1. Launch app → Splash screen (2 seconds)
2. Click "Register"
3. Enter:
   - Full Name
   - Phone Number
   - Email
   - Password (min 6 characters)
   - Confirm Password
4. Click "Create Account"
5. Complete 8-page onboarding:
   - Personal Info
   - Contact Details
   - Financial Info
   - Upload Documents
   - Employment
   - Preferences
   - Security
   - Digital Signature
6. Submit → Main App
```

### Main Features Navigation
**Home Tab:**
- Dashboard overview
- Quick actions
- Account summary

**Transactions Tab:**
- View all 27 transactions
- Filter by category
- Search transactions
- View income/expense details

**Budget Tab:**
- Interactive Pie Chart (spending categories)
- Interactive Bar Chart (monthly trends)
- Click charts for details

**AI Chatbot Tab:**
- Ask financial questions
- Get personalized advice
- Topics: budget, savings, debt, income

**Profile Tab:**
- View user information
- Edit Profile
- Settings
- Logout

### Security Features
**Change Password:**
1. Profile → Settings → Change Password
2. Enter current password
3. Enter new password (min 6 chars)
4. Confirm new password
5. Save

**Change PIN:**
1. Profile → Settings → Change PIN
2. Enter current PIN (4 digits)
3. Enter new PIN (4 digits, numbers only)
4. Confirm new PIN
5. Save

## Key Validations
### Login
- Email format validation
- Password verification against stored credentials
- Error messages for wrong email/password

### Registration
- Full name required
- Phone number required
- Email format validation
- Password minimum 6 characters
- Password confirmation match
- All fields required

### Password Change
- Current password verification
- New password minimum 6 characters
- New password different from current
- Password confirmation match

### PIN Change
- Current PIN verification
- New PIN exactly 4 digits
- New PIN numbers only
- New PIN different from current
- PIN confirmation match


## Dummy Data
### Transactions (27 total)

**Income (2):**
- Salary Payment: $3,500
- Freelance Project: $800
- **Total Income: $4,300**

**Expenses (25):**
- Food & Dining: $450 (6 transactions)
- Transportation: $300 (5 transactions)
- Entertainment: $200 (4 transactions)
- Shopping: $150 (3 transactions)
- Bills & Utilities: $400 (5 transactions)
- Healthcare: $100 (2 transactions)
- **Total Expenses: $1,600**

**Current Balance: $2,700**

### Chart Data
- Pie Chart shows spending distribution
- Bar Chart shows monthly trends ($1,200 - $1,600)
- All data matches transaction list

## Security
### Data Storage
- **SecureStorage** class using EncryptedSharedPreferences
- AES256-GCM encryption
- Secure key generation

### Stored Data
- User credentials (email, password)
- User profile (name, phone)
- User PIN
- Session state
- Onboarding completion status

### Best Practices
- Password minimum length enforced
- PIN format validation
- Current password/PIN verification required
- No plaintext password storage
- Session management
- Secure logout


## 🎨 UI Components

### Colors
```xml
<color name="primary">#2196F3</color>
<color name="primary_dark">#1976D2</color>
<color name="accent">#FF5722</color>
<color name="background">#F5F5F5</color>
<color name="surface">#FFFFFF</color>
<color name="text_primary">#212121</color>
<color name="text_secondary">#757575</color>
```

### Typography
- Titles: 24sp, Bold
- Subtitles: 18sp, Bold
- Body: 16sp, Regular
- Captions: 14sp, Regular
- Small: 12sp, Regular

### Navigation
- Bottom Navigation Bar (5 tabs)
- Tab indicators with icons
- Fragment transitions
- Back navigation support

## Troubleshooting
### Build Errors
**Issue: Gradle sync failed**
```
Solution: File → Invalidate Caches / Restart
```

**Issue: Resource linking failed**
```
Solution: 
1. Build → Clean Project
2. Build → Rebuild Project
```

**Issue: App crashes on launch**
```
Solution:
1. Uninstall old version from device/emulator
2. Clean and rebuild
3. Fresh install
```

### Runtime Issues
**Issue: Login not working**
```
Solution: Use demo credentials or register new account
- Email: admin@neobanking.com
- Password: password123
```

**Issue: Transactions not showing**
```
Solution: Check DummyData.java is properly imported
```

**Issue: Charts not displaying**
```
Solution: Verify MPAndroidChart dependency in build.gradle
```

---

## Screenshots
### Authentication
- Splash Screen with logo
- Login with email/password
- Registration with validation
- Toast notifications

### Onboarding
- 8 progressive pages
- Tab navigation
- Document upload buttons
- Signature pad

### Main App
- Home dashboard
- Transaction list with categories
- Interactive charts
- AI chatbot interface
- Profile with settings

### Settings
- App preferences
- Change password form
- Change PIN form
- Professional UI

## Future Enhancements
### Planned Features
- [ ] Real backend integration
- [ ] Push notifications
- [ ] Card management
- [ ] Bill payments
- [ ] Fund transfers
- [ ] QR code payments
- [ ] Expense analytics
- [ ] Budget goals
- [ ] Investment tracking
- [ ] Credit score monitoring

### Technical Improvements
- [ ] MVVM architecture
- [ ] Dependency injection (Hilt)
- [ ] Room database for offline support
- [ ] Retrofit for API calls
- [ ] Unit tests (JUnit)
- [ ] UI tests (Espresso)
- [ ] CI/CD pipeline
- [ ] Firebase integration
- [ ] Crashlytics

**Glory Mukami**
- GitHub: [@mukamikinyua](https://github.com/mukamikinyua)
- Email: glorymukami2004@gmail.com


## Acknowledgments
- **Material Design** - Google's design system
- **MPAndroidChart** - PhilJay's charting library
- **AndroidX Libraries** - Google's support libraries
- **Stack Overflow** - Community support
- **Android Developers** - Documentation and guides

## Project Stats
- **Total Files:** 100+
- **Lines of Code:** 10,000+
- **Activities:** 8
- **Fragments:** 8
- **Layouts:** 30+
- **Classes:** 25+
- **Features:** 15+

## Tested On
- Android 7.0 (API 24) ✓
- Android 8.0 (API 26) ✓
- Android 9.0 (API 28) ✓
- Android 10 (API 29) ✓
- Android 11 (API 30) ✓
- Android 12 (API 31) ✓
- Android 13 (API 33) ✓
- Android 14 (API 34) ✓


**Made with using Android Studio**

*Last Updated: December 2024*
