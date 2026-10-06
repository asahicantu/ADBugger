[![Stable version](https://img.shields.io/badge/Stable_Version-1.0.5-blue)](https://github.com/Pulimet/ADBugger/releases/latest)
[![License: MIT](https://img.shields.io/badge/License-MIT-brightgreen.svg)](https://github.com/Pulimet/ADBugger/blob/master/LICENSE)
[![Kotlin](https://img.shields.io/badge/Kotlin-2.1.0-green.svg)](https://plugins.gradle.org/plugin/org.jetbrains.kotlin.plugin.compose/2.1.0-Beta2)
[![Compose](https://img.shields.io/badge/Compose-1.7.0-green.svg)](https://github.com/JetBrains/compose-multiplatform/releases/latest)

[![platform - macOS](https://img.shields.io/badge/platform-macOS-000.svg?logo=apple&style=for-the-badge)](https://developer.apple.com/ios)
[![platform - windows](https://img.shields.io/badge/platform-Windows-0067b8.svg?logo=windows&style=for-the-badge)](https://www.microsoft.com/en-us/windows)

ADBugger is a desktop tool for debugging and QA of Android devices and emulators. It simplifies testing, debugging, and performance analysis, offering device management, automated testing, log analysis, and remote control capabilities to ensure smooth app performance across different setups.

*Core Functionality*

- **Device Management:** List connected devices and emulators, and start and stop emulators.
- **Package Management:** Install APKs, list installed apps, and grant and revoke permissions.
- **ADB Commands:** Execute ADB commands on selected targets.
- **Log Management:** View and filter Android device logs (Logcat).
- **Input Simulation:** Send input events (buttons, keyboard) to devices.
- **Port Forwarding:** List and reverse specific ports.
- **One To All:** Execute commands simultaneously on multiple devices.
- **Educating:** Display the underlying commands used.

<img width="600" alt="image" src="https://github.com/user-attachments/assets/500e92a4-384d-4876-adf9-6217af81ad85">

------
**Building and running from source (Windows):**

*Prerequisites*

- **JDK 17 or newer** (JDK 21 recommended). Check with `java -version`.
- **Internet access** on the first build (downloads Gradle 9.8.0 and dependencies).
- **`adb`** (Android platform-tools) on your `PATH`, so the app can talk to devices.
- *Optional:* [WiX Toolset 3.x](https://wixtoolset.org/) to build the `.msi` installer.

*Command line*

```powershell
# Optional: use a specific JDK for this session (e.g. Android Studio's bundled JBR)
$env:JAVA_HOME = "C:\Program Files\Android\Android Studio\jbr"
$env:Path = "$env:JAVA_HOME\bin;$env:Path"

cd ADBugger
.\gradlew.bat run                    # compile and launch the app
```

Other Gradle tasks:

```powershell
.\gradlew.bat build                  # compile and run checks only
.\gradlew.bat createDistributable    # runnable app folder (build\output\)
.\gradlew.bat packageMsi             # Windows installer (requires WiX 3.x)
.\gradlew.bat clean                  # delete build outputs
.\gradlew.bat run --stacktrace       # full stack trace on failure
.\gradlew.bat --stop                 # stop background Gradle daemons
```

*Android Studio / IntelliJ IDEA*

1. **File → Open** and select the project folder, then wait for the Gradle sync.
2. Set **Settings → Build Tools → Gradle → Gradle JDK** to JDK 17 or newer.
3. Run the `run` task under **Gradle → Tasks → compose desktop**, or run `main()` in `src/main/kotlin/Main.kt`.

This is a desktop JVM app, so the Android "Run on device" targets do not apply.

*Troubleshooting*

- **Java version error:** Gradle is using the wrong JDK. Fix `JAVA_HOME` or the Gradle JDK setting.
- **Dependency download failures:** check proxy settings in `~\.gradle\gradle.properties`.
- **No devices shown in the app:** add `<Android SDK>\platform-tools` to `PATH` and verify with `adb devices`.

------
**Roadmap:**
- https://github.com/users/Pulimet/projects/1
------
**Release notes:**
- https://github.com/Pulimet/ADBugger/releases
------
