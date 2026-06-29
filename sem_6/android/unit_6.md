# Deployment, Maintenance, and App Security

## APK and ABB

### APK - Android Package Kit

- installable file format for android apps
- contains all codes, resources and assets
- `.apk` file extention

### AAB - Android App Bundle

- file format used for releasing apps in play store
- contains everything needed to run the app
- play store generates optimized APK's for each device
- smaller download sizes

### APK vs ABB

| Debug APK                       | Release AAB                          |
| ------------------------------- | ------------------------------------ |
| during development and testing. | publishing apps.                     |
| debugging information and logs. | production use.                      |
| Larger file size.               | Smaller download size for users.     |
| Signed with a debug key.        | Signed with a release key.           |
| Lower performance.              | Better performance and optimization. |
| no Play Store                   | for Play Store                       |

## OTA Updates → Over the Air Updates

- allow developers to send updates directly
- receive updates without downloading new version
- React Native → OTA updates JS code and assets

### Working

Developer → OTA server → User app downloads the update

### Prefer OTA Updates when

- small bug fixes
- UI changes
- text or content update
- JS logic updates

### Prefer store updates when

- native or IOS code changes
- adding new permissions
- updating native libraries
- major feature drops

  | OTA Updates                        | Store Updates                  |
  | ---------------------------------- | ------------------------------ |
  | Over-The-Air updates               | via Play Store/App Store       |
  | No store approval required         | Requires store approval        |
  | Delivered directly over internet   | Downloaded from app stores     |
  | Faster deployment                  | Slower deployment              |
  | Updates JS code and assets only    | Updates the entire application |
  | Cannot update native code          | Can update native code         |
  | Suitable for bug fixes, UI changes | Suitable for major releases    |

## JWT Rotation

- JWT → JSON web token
- use two tokens:
  1. access token
  2. refresh token
- when access token expires, refresh token generates a new one
- the old replace token is replaced with a new one (rotation)
- improves security if token is stolen

## Biometrics

- auth using
  1. fingerprint
  2. face ID
  3. touch ID

```
1. User logs in with Email + Password
                    ↓
2. Server generates:
   - Access Token
   - Refresh Token
                    ↓
3. Access Token stored in memory
   Refresh Token stored securely
   (Keychain / Keystore)
                    ↓
4. User closes app and comes back later
                    ↓
5. User verifies identity using:
   - Fingerprint OR
   - Face ID
                    ↓
6. Biometrics unlock the stored
   Refresh Token
                    ↓
7. App sends Refresh Token to server
                    ↓
8. Server generates:
   - New Access Token
   - New Refresh Token
                    ↓
9. Old Refresh Token is invalidated
   (JWT Rotation)
                    ↓
10. User is logged in automatically
```

### How they improve security

1. JWT Refresh tokens:

- access tokens short lived
- refresh tokens used to generate new access token
- users do not need to enter credentials repeatedly
- rotation invalidates old tokens
- reduces impact of stealing

1. Biometric Authentication

- fingerprint / Face ID
- prevents unauthorized access
- eliminates need to store password
- protects access to stored refresh tokens

## Runtime Permissions

- permissions requested when app is running
- introduced in android 6
- used for sensitive features (camera, mic, location, etc)

### Permission flow

```
App needs Camera Access
↓
Check if permission is granted
↓
Yes ----------> Use Camera
↓ No
Show permission dialog
↓
User selects:
Allow / Deny
↓
If Allowed ---> Access resource
If Denied ----> Show message or disable feature
```

#### Android Flow

1. declare perms in `AndroidManifest.xml`
2. check perms during runtime
3. request perms if not granted
4. handle user response

#### React Native flow

1. use the `PermissionAndroid` API
2. common methods: `check()`, `request()`, `requestMultiple()`

eg:

```jsx
const granted = await PermissionsAndroid.request(
  PermissionsAndroid.PERMISSIONS.CAMERA,
);
```

## Best Practices for Runtime Permissions

- Request permissions only when needed, not at app startup.
- Explain to users why the permission is required before requesting it.
- Check if permission is already granted before requesting again.
- Handle both Allow and Deny cases gracefully.
- Provide fallback functionality if permission is denied.
- Request only the permissions necessary for the feature.
- Handle the "Don't Ask Again" scenario by guiding users to app settings.
- Use `PermissionsAndroid` or permission libraries for management.
- Follow platform guidelines for privacy and security.

| Storage Option    | Use Case                                         |
| ----------------- | ------------------------------------------------ |
| MMKV              | Fast local storage and caching                   |
| Encrypted Storage | Secure storage of sensitive data                 |
| Keychain/Keystore | Highly secure storage for credentials and tokens |
