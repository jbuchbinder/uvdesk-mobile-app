## Build Environment
- Flutter 3.41.9 (stable), Android SDK at ~/Code/Android, Flutter SDK at /opt/flutter
- AGP 8.11.1, Kotlin 2.2.20, Gradle 8.14, Java 17 — all required for this Flutter version
- `android.newDsl=false` in gradle.properties is required (AGP 9+ DSL is incompatible)

## Common Build Issues
- Many pub-cached plugins (file_picker, permission_handler, battery, connectivity, etc.) still reference removed V1 embedding `PluginRegistry.Registrar` — remove `registerWith()` and the import, simplify setup() to V2-only path
- Old plugins may lack `namespace` in build.gradle — add one matching their package
- Old plugins with `compileSdkVersion 28-31` will fail AAPT linking (lStar not found) — bump to `compileSdk 34`
- `easy_search_bar` 2.5.0 has Flutter 3.x API breakage (`AppBarTheme` → `AppBarThemeData`, `headline6` → `titleLarge`)

## Disk Space
- ~/.gradle/caches can grow large (5GB+); clear if `No space left on device` during SDK installs
- Trash (~/.local/share/Trash) and ~/.cache/winetricks are also common space hogs on this machine
