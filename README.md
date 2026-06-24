# DailyDo – Android Wellness App

DailyDo is a Kotlin-based Android wellness application designed to help users build positive routines, track daily habits, record moods, monitor hydration, and visualize personal progress.

The application was developed in Android Studio as part of the **IT2010 – Mobile Application Development** module at SLIIT.

## Overview

DailyDo brings several personal-wellness tools into one mobile application.

Users are introduced to the application through a three-screen onboarding flow that explains the main features:

* Daily habit tracking
* Mood journaling
* Wellness analytics and progress visualization

The application uses a simple bottom-navigation structure to provide access to habits, mood tracking, and hydration monitoring.

## Features

### Splash and Onboarding

* Branded DailyDo splash screen
* Three onboarding screens
* Introduction to habit tracking
* Introduction to mood monitoring
* Introduction to wellness analytics
* Start button leading to the main application

### Daily Habit Tracker

Users can:

* Create new habits
* Assign a time to each habit
* Display habits in a list
* Mark habits as completed
* Delete habits
* Track the current day’s completion percentage
* View habit progress through an analytics graph

Habit data and completion information are stored locally using `SharedPreferences`.

### Mood Journal

The mood-journal feature allows users to:

* View moods in a monthly calendar
* Navigate between months
* Select a date
* Choose an emoji representing their mood
* Add an optional note
* Save mood entries locally
* View previously recorded moods directly on the calendar

The application prevents users from adding mood entries for future dates.

### Hydration Monitoring

The hydration section includes:

* Selectable hydration intervals
* Short demonstration intervals for testing
* Longer practical intervals
* Circular countdown/progress indicator
* Visual indication when the selected interval is complete

Available intervals include options such as:

* 10 seconds
* 15 seconds
* 20 seconds
* 30 minutes
* 45 minutes
* 1 hour
* 1 hour 30 minutes
* 2 hours

### Progress Analytics

DailyDo includes an analytics screen that displays habit-completion progress over time.

The graph helps users:

* Review completion percentages
* Observe consistency
* Identify personal habit trends
* Stay motivated through visual feedback

### Home-Screen Widget

The project contains a home-screen widget implementation for displaying habit-related progress information outside the main application.

## Application Flow

```text
Splash Screen
      ↓
Onboarding Screen 1
      ↓
Onboarding Screen 2
      ↓
Onboarding Screen 3
      ↓
Main Application
      ↓
Home / Mood / Hydration
```

The main navigation structure is:

```text
Home
 ├── Add Habit
 ├── Complete Habit
 ├── Delete Habit
 └── View Analytics

Mood
 ├── Browse Calendar
 ├── Select Date
 ├── Select Emoji
 └── Add Optional Note

Hydration
 ├── Select Interval
 ├── Start Countdown
 └── View Completion Status
```

## Main Screens

The application includes:

1. Splash screen
2. Onboarding screen 1
3. Onboarding screen 2
4. Onboarding screen 3
5. Main habit-tracking screen
6. Add-habit bottom sheet
7. Habit analytics graph
8. Mood calendar
9. Add-mood bottom sheet
10. Hydration monitoring screen
11. Home-screen widget

## Technology Stack

* Kotlin
* Android Studio
* Android SDK
* XML layouts
* Gradle Kotlin DSL
* Android Activities
* Android Fragments
* RecyclerView
* Bottom Navigation
* SharedPreferences
* JSON-based local data storage
* AlarmManager
* BroadcastReceiver
* App Widgets
* Git
* GitHub

## Architecture and Organization

The application uses Activities and Fragments to separate the major features.

Important project components include:

* `MainActivity`
* `SplashScreen`
* `HabitActivity`
* `HabitGraphActivity`
* `DailyHabitFragment`
* `MoodFragment`
* `HydrationFragment`
* `HabitAddBottomSheetFragment`
* `HabitAdapter`
* `HabitPreference`
* `MoodPreference`
* `AlarmReceiver`
* `HabitWidget`
* `WidgetUpdateUtil`

Models are used for habit and mood data:

* `Habit`
* `MoodEntry`

## Data Persistence

DailyDo stores its application data locally using `SharedPreferences`.

This includes:

* Habit information
* Habit completion status
* Mood entries
* Mood notes
* Date-related mood information

No external database or production backend is required for the current version.

## Simplified Project Structure

```text
DailyDo-Android-Wellness-App/
│
├── app/
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/com/example/myapplication/
│   │   │   │   ├── adapter/
│   │   │   │   ├── db/
│   │   │   │   ├── fragment/
│   │   │   │   ├── model/
│   │   │   │   ├── utils/
│   │   │   │   ├── MainActivity.kt
│   │   │   │   ├── SplashScreen.kt
│   │   │   │   ├── HabitActivity.kt
│   │   │   │   ├── HabitGraphActivity.kt
│   │   │   │   ├── HabitWidget.kt
│   │   │   │   └── AlarmReceiver.kt
│   │   │   ├── res/
│   │   │   │   ├── drawable/
│   │   │   │   ├── layout/
│   │   │   │   ├── menu/
│   │   │   │   ├── mipmap/
│   │   │   │   ├── values/
│   │   │   │   └── xml/
│   │   │   └── AndroidManifest.xml
│   │   ├── androidTest/
│   │   └── test/
│   ├── build.gradle.kts
│   └── proguard-rules.pro
│
├── gradle/
├── .gitignore
├── build.gradle.kts
├── gradle.properties
├── settings.gradle.kts
└── README.md
```

## Requirements

To build and run the project, install:

* Android Studio
* Android SDK
* Java Development Kit supported by Android Studio
* Git
* Android emulator or physical Android device

Project configuration:

* Minimum SDK: 24
* Target SDK: 36
* Compile SDK: 36
* Gradle wrapper: 8.13
* Kotlin JVM target: 11

## Setup Instructions

Clone the repository:

```bash
git clone https://github.com/naily247/DailyDo-Android-Wellness-App.git
```

Move into the project directory:

```bash
cd DailyDo-Android-Wellness-App
```

Open the project in Android Studio:

1. Launch Android Studio.
2. Select **Open**.
3. Choose the cloned project folder.
4. Allow Gradle synchronization to complete.
5. Wait for indexing and dependency downloads to finish.

Android Studio will create a machine-specific `local.properties` file containing the Android SDK path.

## Build Instructions

### Android Studio

1. Open the project.
2. Complete Gradle synchronization.
3. Select **Build**.
4. Select **Assemble Project**.

### macOS or Linux Terminal

```bash
./gradlew assembleDebug
```

If direct execution is unavailable:

```bash
bash gradlew assembleDebug
```

### Windows

```powershell
gradlew.bat assembleDebug
```

## Run Instructions

1. Open the project in Android Studio.
2. Start an Android emulator or connect a physical device.
3. Select the `app` run configuration.
4. Select the target device.
5. Click **Run**.

The project has been successfully built and tested using a Pixel 8 Pro emulator.

## Testing Status

The following were manually verified:

* Gradle synchronization
* Clean project operation
* Debug build
* Application launch
* Splash screen
* All three onboarding screens
* Main navigation
* Habit creation
* Habit display
* Habit completion
* Habit deletion
* Daily completion percentage
* Habit analytics graph
* Mood calendar
* Month navigation
* Emoji selection
* Optional mood notes
* Stored mood display
* Hydration interval selection
* Circular hydration countdown
* Main application pages and navigation

The application currently builds successfully without blocking compilation errors.

## Current Limitations

The current version is an educational Android application and may have the following limitations:

* No cloud-based user accounts
* No external backend
* No online database
* No synchronization across devices
* Data is stored only on the local device
* No production-ready authentication system
* Hydration scheduling may depend on device and Android-version behavior
* Limited automated unit and UI tests
* No Play Store release configuration
* No production signing setup

## Future Improvements

Possible future enhancements include:

* Firebase Authentication
* Cloud Firestore integration
* Cross-device synchronization
* Improved hydration notifications
* Reminder persistence after device restart
* Configurable notification settings
* More detailed habit categories
* Habit streak tracking
* Weekly and monthly analytics
* Expanded mood statistics
* Mood trend charts
* Dark mode
* Improved tablet layouts
* Accessibility improvements
* Automated unit tests
* Automated UI tests
* Jetpack Compose migration
* MVVM architecture
* ViewModel and StateFlow
* Repository pattern
* Production release signing
* Google Play publishing

## Security and Gitignore

The repository includes an Android-specific `.gitignore`.

The following are excluded from version control:

* `.gradle/`
* `.idea/`
* `local.properties`
* Build folders
* APK files
* AAB files
* Signing keys
* Keystore files
* Logs
* Temporary files
* Editor-specific workspace files
* Local AI workspace notes

Sensitive information such as SDK paths, signing credentials, keystores, API keys, and passwords should never be committed to the repository.

## Repository

```text
https://github.com/naily247/DailyDo-Android-Wellness-App
```

## Academic Context

This project was developed for:

* Module: IT2010 – Mobile Application Development
* Programme: BSc (Hons) in Information Technology
* Institution: SLIIT
* Academic year: 2025
* Assessment: Lab Exam 03

## Author

**Naily Ashvitha**

Student ID: `IT23654358`

GitHub: `naily247`

## License

This project is provided for educational and portfolio purposes.

No formal open-source license has currently been added. Until a license is included, all rights remain with the project author.
