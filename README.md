# uv_desk_flutter_open_source

UVDesk open source Flutter mobile application for Android.

## Prerequisites

- **Flutter SDK** 3.41+ (stable channel)
- **Android SDK** with build-tools 35, platform 33, NDK 28
- **Java** 17 (required by AGP 8.x)
- **Gradle** 8.14 (wrapper included in `android/gradle/wrapper/`)

## Dependencies

### Core
| Package | Purpose |
|---------|---------|
| `flutter_bloc` / `bloc` | State management |
| `dio` / `retrofit` | HTTP client and API layer |
| `floor` / `hive` | Local database and storage |
| `json_annotation` / `json_serializable` | JSON code generation |
| `get_storage` | Simple key-value storage |
| `permission_handler` | Runtime permissions |
| `file_picker` | File selection dialogs |
| `easy_search_bar` | Search bar widget |
| `path_provider` / `downloads_path_provider_28` | Filesystem path access |
| `upgrader` | In-app update prompts |
| `simple_animations` | UI animations |
| `cupertino_icons` | iOS-style icons |
| `flutter_localizations` | i18n support |
| `logger` | Logging |
| `equatable` | Value equality |
| `mime` / `html` | MIME type detection and HTML parsing |

### Patched local packages
Several transitive plugins required compatibility fixes for Flutter 3.41+ and AGP 8.x.
These are vendored under `local_packages/` and wired via `path:` and `dependency_overrides` in `pubspec.yaml`:

- `easy_search_bar-2.5.0` — Flutter 3.x API updates (AppBarTheme, TextTheme)
- `file_picker-5.5.0` — V2 Android embedding migration
- `downloads_path_provider_28-0.1.2` — V2 embedding, compileSdk, namespace
- `permission_handler_android-10.3.6` — V2 embedding
- `path_provider_android-2.2.1` — V2 embedding, compileSdk
- `url_launcher_android-6.2.1` — V2 embedding
- `flutter_plugin_android_lifecycle-2.0.17` — V2 embedding

## Build Instructions

```bash
# 1. Install dependencies
flutter pub get

# 2. Build APK
flutter build apk

# Output: build/app/outputs/flutter-apk/app-release.apk
```

For a debug build:

```bash
flutter build apk --debug
```

## Configuring the App

The below mentioned files will help you with the configuration of the code.

- [server_configuration.dart](https://github.com/uvdesk/mobile_app/blob/main/lib/mobikul-uvdesk/configuration/server_configuration.dart)
  Change the three variables `baseUrl`, `demoUserName`, `demoPassword` as per your use.
- [mobikul_theme.dart](https://github.com/uvdesk/mobile_app/blob/main/lib/mobikul-uvdesk/configuration/mobikul_theme.dart)
  Change the colors as per your need.

## Complete User Guide

To read more about the features of the app, please visit the article [here](https://www.uvdesk.com/en/blog/uvdesk-open-source-flutter-mobile-app/).

# App Screenshots

#### Login Screen
![login_screen](screenshots/login_screen.png)

#### Agent Profile View
![agent_profile](screenshots/agent_profile.png)

#### List View
![ticket_list](screenshots/ticket_list.png)

#### Ticket Details View
![ticket_details](screenshots/ticket_details.png)

#### Ticket Reply View
![ticket_reply](screenshots/ticket_reply.png)

#### Ticket Status Update View
![ticket_status](screenshots/ticket_status.png)

#### Ticket Activity View
![ticket_log](screenshots/ticket_log.png)

#### Customer Information View
![customer_info](screenshots/customer_info.png)
