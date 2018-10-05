---
title: "React Native"
subtitle: "SDK for screen recording and analytics for React Native."
---

With this SDK developers and/or companies should be able to:

* Replay session recordings in our web player
* See app structure as an ordered graph where nodes are unique screens
* Set their own custom analytics event and do complex funnels/queries in the dashboard
* Get automatic crash reports

## Getting started

1. `$ npm install smartlook-react-native-wrapper --save`
2. `$ react-native link smartlook-react-native-wrapper`

### iOS

1. `$ pod init` - can be skipped in case you are already using pods
2. Add `pod 'Smartlook'` to your Podfile
3. `$ pod install`

### Android

1. Open `android/build.gradle`
2. Update gradle version to `classpath 'com.android.tools.build:gradle:3.1.0'`
3. Add our maven repository:

```android
allprojects {
  repositories {
    maven {
      url "https://sdk.smartlook.com/android/release"
    }
  }
}
```

Also edit `gradle-wrapper.properties` so you are using: `gradle-4.4-all.zip`

## Usage

```js
var Smartlook = require('smartlook-react-native-wrapper');
Smartlook.init("KEY");
```

Description of additional public SDK methods can be found i.e. in <a href="https://smartlook.github.io/docs/sdk/android/">Android</a> docs section.