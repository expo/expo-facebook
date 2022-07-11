# expo-facebook

> Source code for the deprecated expo-facebook package. This module is removed from Expo SDK in SDK 46. There will be no replacement that works with the classic build service (`expo build`) because [the classic build service has been superseded by **EAS Build**](https://blog.expo.dev/turtle-goes-out-to-sea-d334db2a6b60). With **EAS Build** and [Development Builds](/development/introduction.md), you should use [react-native-fbsdk-next](https://github.com/thebergamo/react-native-fbsdk-next/#expo-installation) instead.

Expo universal module for Facebook SDK

# Installation in bare React Native projects

For bare React Native projects, you must ensure that you have [installed and configured the `expo` package](https://docs.expo.dev/bare/installing-expo-modules/) before continuing.

### Add the package to your npm dependencies

```
expo install expo-facebook
```

### Configure for iOS

Run `npx pod-install` after installing the npm package.

Add `NSUserTrackingUsageDescription` key to your `Info.plist`:

```xml
<key>NSUserTrackingUsageDescription</key>
<string>This identifier will be used to deliver personalized ads to you.</string>
```

Add the required `SKAdNetworkIdentifier` items to your `Info.plist`: [Facebook SKAdNetwork](https://developers.facebook.com/docs/SKAdNetwork).

Finally, create a blank Swift file in your project (we recommend naming it `noop-file.swift`). Learn more: [FBSDK blank Swift file](https://github.com/facebook/react-native-fbsdk/issues/755).

### Configure for Android

No additional set up necessary.

In `AndroidManifest.xml`, add the following element within your `<application>` element:

```xml
...
      <!-- The Facebook SDK runs FacebookInitProvider on startup and crashes if there isn't an ID here -->
    <meta-data android:name="com.facebook.sdk.ApplicationId" android:value="fb0"/>
  </application>
```