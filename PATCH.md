# fork of `hms_room_kit`

**Upstream:** `hms_room_kit` 1.2.0 (100ms).

**Change:** `lib/src/common/utility_functions.dart` — `checkPermissions()` and `getPermissions()` require **camera + microphone only**. Upstream also required Bluetooth (iOS) and phone (Android), which blocked many users who call over the phone speaker. `checkPermissions()` **requests camera + mic and then reads `.status`** so the plugin matches system Settings (some iOS/Android builds reported `denied` until `request()` had run).

**Maintenance:** When bumping `hmssdk_flutter` / `hms_room_kit`, replace this folder with the new pub.dev version and re-apply the same edit, or merge upstream if they make Bluetooth optional.
