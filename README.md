# Artists & Bands — Android — College Project

> College coursework project, preserved as a record of learning and academic development.

An Android application for managing artists, bands, and band membership, built with **Java** and **Firebase Realtime Database**. Originally named **Evento_**, the project includes groundwork for event management. The implemented screens focus on artists and bands, with an interface in Portuguese.

## Features

- Create and edit artists with their names and roles.
- List and delete artists using selection controls and confirmation dialogs.
- Create, edit, list, and delete bands.
- Add registered artists to a band and remove members while editing.
- Persist artist and band records in Firebase Realtime Database.

## Technology

| Component | Configuration in this repository |
| --- | --- |
| Language | Java, source compatibility 1.8 |
| UI | Android Views, AndroidX, Material Components, RecyclerView |
| Storage | Firebase Realtime Database |
| Data serialization | Gson |
| Android SDK | Compile / target 32; minimum 23 |
| Build | Gradle 7.3.3 / Android Gradle Plugin 7.2.1 |

## Getting started

1. Clone the repository:

   ```bash
   git clone https://github.com/EmanuelCChagas/college-artists-and-bands-android.git
   ```

2. Open the repository root in Android Studio. Use a Gradle JDK compatible with the checked-in build configuration and install Android SDK Platform 32.
3. Configure a Firebase project with an Android app registered as `com.howiv.evento_`.
4. Replace `app/google-services.json` with the configuration downloaded for your own Firebase project.
5. Set up Firebase Realtime Database. The app reads and writes the top-level `Artistas` and `Bandas` nodes. Database access rules must account for the fact that the current app has no authentication flow; use an isolated development backend.
6. Sync Gradle and run the `app` configuration on an emulator or device. Use API 24 or later for the current artist-selection code, which calls Java stream APIs despite the declared minimum SDK of 23.

To assemble a debug APK after configuring the Android SDK and Firebase:

```bash
# Linux / macOS
bash gradlew assembleDebug
```

```bat
:: Windows
gradlew.bat assembleDebug
```

## Source guide

- [Activities](app/src/main/java/com/howiv/evento_): main menu and artist/band screens.
- [Models](app/src/main/java/com/howiv/evento_/model): `Artista`, `Banda`, and the initial `Evento` model.
- [Adapters](app/src/main/java/com/howiv/evento_/adapter): list rendering and selection.
- [Layouts](app/src/main/res/layout): XML screen and list-item layouts.
- [App build configuration](app/build.gradle): SDK versions and dependencies.

## Project status

Event management is unfinished: `MainActivity.abrirEventos()` is empty. An event model, adapter, and layout exist, but there is no complete event-management screen. The repository includes generated example tests rather than comprehensive feature tests. The historical Firebase configuration is included, but availability of that backend is not established.
