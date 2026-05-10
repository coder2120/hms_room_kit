# fork of `hms_room_kit`

**Upstream:** `hms_room_kit` 1.2.0 (100ms).

**Changes:**

1. **`lib/src/common/utility_functions.dart`** — `checkPermissions()` and `getPermissions()` require **camera + microphone only**. Upstream also required Bluetooth (iOS) and phone (Android), which blocked many users who call over the phone speaker. `checkPermissions()` **requests camera + mic and then reads `.status`** so the plugin matches system Settings (some iOS/Android builds reported `denied` until `request()` had run).

2. **`lib/src/meeting/meeting_store.dart` (Spedia Uni / Academy app)** — On successful `HMSActionResultListenerMethod.startScreenShare`, auto-mute the **local camera**; on `stopScreenShare`, restore video if it was muted for that reason (reduces encode/uplink while sharing screen).

**Maintenance:** When bumping `hmssdk_flutter` / `hms_room_kit`, replace from the new pub.dev (or 100ms monorepo) release and re-apply these edits, or merge upstream if they adopt the same behavior.
