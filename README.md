# FitTrack Pro — Android source project

## Included in this first implementation
- Kotlin + Jetpack Compose Android app
- Daily dashboard with a 10,000-step goal
- Health Connect permission flow and today's step aggregation
- Local offline logging for food calories, workouts, water, weight, sleep and habits
- Progress snapshot and coach tip
- Dark navy / green fitness interface

## Build
1. Install Android Studio (current stable) and Android SDK 35.
2. Open this folder as an existing Gradle project.
3. Use JDK 17.
4. Let Gradle sync, then Build > Build Bundle(s) / APK(s) > Build APK(s).
5. Install the generated APK on an Android device.

## Health Connect
- Install/update Health Connect on the phone if needed.
- Open FitTrack Pro > Today or Settings > Connect / sync.
- Grant the Steps permission.
- The app reads today's step aggregate from Health Connect when you tap sync.
- A compatible phone/watch/app must write step records to Health Connect for data to appear.

## Current scope / honest limitations
This is a functional starter release, not a finished Play Store product.
- Step data is imported on demand; background automatic sync is not yet implemented.
- Food, water, weight, sleep, habits and workout totals are stored locally in SharedPreferences.
- The first version stores a daily total for food calories and workout minutes, not a detailed multi-day journal.
- Workout logging currently adds a 30-minute session; detailed exercise sets/reps and history are a next-stage feature.
- No calorie-burn estimate is presented as measured data.
- Notifications, backup, charts over time, data export, profile onboarding and privacy policy need to be added before public release.
- Health Connect availability and permissions vary by Android version and device.

## Suggested next release
Add Room database with date-stamped records, background step sync, Health Connect sleep/weight reads, reminder scheduling, configurable calorie/protein targets, weekly trend charts, and export/backup.


## Build an APK using GitHub Actions
1. Create a GitHub repository and upload the contents of this project.
2. Ensure the default branch is named `main`.
3. Open the repository's **Actions** tab.
4. Select **Build FitTrack Pro APK** and click **Run workflow** (or push a commit to `main`).
5. When the workflow finishes, open its run and download the `FitTrackPro-debug-apk` artifact.
6. Extract `app-debug.apk` and transfer it to your Android phone to install.

This workflow creates a debug-signed APK for testing. A Play Store release should use a separately configured release signing key.
