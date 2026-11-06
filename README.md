## 🚀 Features

* **Dashboard / Home Screen:** Provides an overview of total balances, financial summaries, recent transactions, and quick action shortcuts.
* **Transaction Management:** Easily add, edit, categorize, and delete income, expenses, transfers, and loans.
* **Financial & Saving Goals:** Set target saving goals, monitor progress, and manage dedicated savings.
* **Reports & Analytics:** Visualized spending and income breakdowns to track financial habits over time.
* **Currency Converter:** Built-in utility to convert currencies on the go.
* **Loan & Debt Reminders:** Scheduled reminders and notifications for loans and debts using Android AlarmManager and WorkManager.
* **Notifications Center:** Central hub to view and manage alerts, reminders, and app updates.
* **Settings & Customization:** Preferences for accounts, currencies, dark/light themes, and sidebar configurations.
* **Onboarding & Splash Screen:** Interactive introductory walkthrough for first-time users.
* **In-App Updates:** Integrated Google Play App Update support to keep the app up to date.

## 🛠️ Tech Stack

* **Language:** Kotlin (JVM Target 21)
* **UI Framework:** Jetpack Compose with Material 3 design system.
* **Architecture:** MVVM (Model-View-ViewModel) pattern with reactive state management.
* **Dependency Injection:** Dagger Hilt & Hilt WorkManager integration.
* **Local Database:** Room Database for robust offline data persistence.
* **Asynchronous Programming:** Kotlin Coroutines & StateFlow / SharedFlow.
* **Navigation:** Jetpack Navigation Compose.
* **Image Loading:** Coil Compose.
* **Background Processing:** WorkManager & BroadcastReceivers for scheduled alarms/reminders.
* **Play Services:** Google Play App Update KTX.


## 📂 Project Structure

```text
com.dyiz.smart.wallet/
│
├── data/                     # Local data layer
│   ├── converter/            # Room type converters (e.g., Converters.kt)
│   ├── dao/                  # Database Data Access Objects (AccountDao, TransactionDao, NotificationDao)
│   ├── database/             # Room AppDatabase instance
│   ├── entity/               # Room entities (Account, Transaction, SavingGoal, Notification)
│   └── repo/                 # Repository classes (TransactionRepository)
│
├── di/                       # Dependency Injection modules (DatabaseModule, etc.)
│
├── receiver/                 # Broadcast receivers for alarms & notifications (LoanReminderReceiver)
│
├── ui/                       # User Interface layer
│   ├── feature/screens/      # Compose screens (Home, Transactions, Add Transaction, Goals, Reports, Currency Converter, Notifications, SettingsSidebar, Onboarding, Splash)
│   ├── navigation/           # Navigation graph and routes (AppNavGraph, NavRoutes)
│   ├── theme/                # Material 3 theme, colors, typography, and fonts
│   └── viewmodel/            # ViewModels managing UI state (TransactionViewModel, NotificationViewModel)
│
├── util/                     # Utility helpers & managers (AlarmScheduler, CurrencyManager, Account/Notification Preferences, PermissionHelper, AppUpdateHelper)
│
├── BudgetTrackApp.kt         # Custom Application class (@HiltAndroidApp)
└── MainActivity.kt           # Main Activity hosting the Compose UI


## 📱 Requirements & System Specifications

### 🔹 System Requirements
* **OS Compatibility:** Android 7.0 (API Level 24) or higher.
* **SDK Versions:** Min SDK: 24 | Target SDK: 36.
* **Layout:** Optimized for portrait orientation.

### 🔐 Device Permissions
* **`POST_NOTIFICATIONS`:** Required on Android 13+ to display transaction reminders and alerts.
* **`SCHEDULE_EXACT_ALARM` / `USE_EXACT_ALARM`:** Required to trigger precise loan and debt reminder alarms.

### 🛠️ Development Requirements (Building from Source)
* **IDE:** Android Studio (Koala / Jellyfish or newer).
* **Language & Runtime:** JDK 21 / Kotlin 2.x.
* **Build System:** Gradle build system.
