---
layout: default-layout
title: Build with Expo
description: This is the user guide of Dynamsoft Barcode Reader React Native SDK for Expo projects.
keywords: user guide, React Native, Expo, barcode
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Barcode Reader Integration Guide for Expo

This guide will help you develop a barcode scanning app with Expo project.

> [!Important]
>
> This SDK uses native modules and **requires an Expo development build**. It will **not work with Expo Go**.
> To use it with Expo, you must use **Expo Bare Workflow**.

```bash
npx expo prebuild
npx expo install dynamsoft-capture-vision-react-native dynamsoft-barcode-reader-bundle-react-native
npx expo run:android / ios
```

## System Requirements

- Expo
  - Supported SDK: 50 or higher
  - Requires Expo development build (Expo Go is not supported)
- React Native
  - Supported Version: 0.71.0 or higher
- Android
  - Supported OS: Android 5.0 (API Level 21) or higher.
  - Supported ABI: armeabi-v7a, arm64-v8a, x86 and x86_64.
  - Development Environment:
    - IDE: **Android Studio 2024.3.2** suggested.
    - JDK: **Java 17** or higher.
    - Gradle: **8.0** or higher.
- iOS
  - Supported OS: iOS 13+.
  - Supported ABI: arm64 and x86_64.
  - Development Environment: Xcode 13+ (Xcode 14.1+ recommended).

## License Activation

License is configured via `LicenseManager`. For example:

```tsx
const License = 'DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9';
LicenseManager.initLicense(License).catch(e => {
  Alert.alert('License error', e.message);
});
```

## Build Your Barcode Scanner App

### Preparation

1. Create a new Expo project with the following command:

    ```bash
    npx create-expo-app ScanBarcodes
    cd ScanBarcodes
    ```

2. Follow the [installation section](#installation) to install the dependencies and generate native projects.

### Installation

Run the following commands in the root directory of your Expo project to add the required dependencies:

```bash
npx expo install dynamsoft-capture-vision-react-native dynamsoft-barcode-reader-bundle-react-native
```

Add the `dynamsoft-capture-vision-react-native` plugin to the `app.json` file:

```json
"plugins": [
    "dynamsoft-capture-vision-react-native",
    //....
]
```

Since your app requires camera access, you need to add `NSCameraUsageDescription` to the `ios` section of `app.json`:

```json
    "ios": {
      "infoPlist": {
        "NSCameraUsageDescription": "This app uses the camera to scan barcodes."
      }
    },
```

Since this SDK requires native code, you need to generate the native projects:

```bash
npx expo prebuild
```

For iOS, install the CocoaPods dependencies:

```bash
cd ios
pod install
cd ..
```

### Implementing the Barcode Scanner

New Expo projects use [Expo Router](https://docs.expo.dev/router/introduction/) with a file-based routing system. The main entry point is located in the `app` folder instead of a root `App.tsx` file.

Replace the content of `app/(tabs)/index.tsx` with the following code:

```tsx
import {
  CameraEnhancer,
  CameraView,
  CaptureVisionRouter,
  EnumPresetTemplate,
  LicenseManager,
} from 'dynamsoft-capture-vision-react-native';
import React, {useEffect, useRef} from 'react';
import {Alert, AppState, StyleSheet, View} from 'react-native';
// Initialize the license.
// The license string here is a trial license. Note that network connection is required for this license to work.
// You can request an extension via the following link: https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=samples&package=react-native
const License = 'DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9';
LicenseManager.initLicense(License).catch(e => {
  Alert.alert('License error', e.message);
});

function App(): React.JSX.Element {
  const cameraView = useRef<CameraView>(null!);
  const cvr = CaptureVisionRouter.getInstance();
  const camera = CameraEnhancer.getInstance();

  useEffect(() => {
    // Request camera permission once
    CameraEnhancer.requestCameraPermission();

    // Configure router, camera and view
    cvr.setInput(camera);
    camera.setCameraView(cameraView.current);

    // Barcode result handler
    const receiver = cvr.addResultReceiver({
      onDecodedBarcodesReceived: ({items}) => {
        if (items?.length) {
          cvr.stopCapturing();
          Alert.alert(
            `Barcodes count: ${items.length}`,
            items.map((barcode, i) => `${i + 1}. ${barcode.formatString}: ${barcode.text}`).join('\n\n'),
            [
              {
                text: 'OK',
                onPress: () => {
                  cvr.startCapturing(EnumPresetTemplate.PT_READ_BARCODES)
                    .catch(e => Alert.alert('Start error', e.message));
                }
              }
            ]
          );
        }
      },
    });

    // Helper to start camera + scanning
    const startScanning = () => {
      console.log('Starting...');
      camera.open();
      cvr.startCapturing(EnumPresetTemplate.PT_READ_BARCODES)
        .catch(e => Alert.alert('Start error', e.message));
    };

    // Helper to stop camera + scanning
    const stopScanning = () => {
      console.log('Stopping...');
      cvr.stopCapturing();
      camera.close();
    };

    // Initial start when component mounts
    startScanning();

    // Listen to AppState changes
    const sub = AppState.addEventListener('change', nextState => {
      if (nextState === 'active') {
        startScanning();
      } else if (nextState.match(/inactive|background/)) {
        stopScanning();
      }
    });

    // Cleanup on unmount
    return () => {
      sub.remove();
      stopScanning();
      cvr.removeResultReceiver(receiver);
      camera.setCameraView(null);
    };
  }, [cvr, camera]);

  return (
    <View style={StyleSheet.absoluteFill}>
      <CameraView style={StyleSheet.absoluteFill} ref={cameraView}/>
    </View>
  );
}

export default App;
```

> [!Note]
>
> - The LICENSE string here grants a time-limited free trial which requires network connection to work.
> - You can request a 30-day trial license via the [Request a Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=guide&package=react-native){:target="_blank"} link.
> - If you download the <a href="https://www.dynamsoft.com/barcode-reader/downloads/?utm_source=docs#mobile" target="_blank">Installation Package</a>, it comes with a 30-day trial license by default.

### Run the App

#### Build and Run on Android

For Android, run the following command:

```bash
npx expo run:android
```

For iOS, run the following command:

```bash
npx expo run:ios
```

## Full Sample Code

The full sample code is available [here](https://github.com/Dynamsoft/barcode-reader-react-native-samples/tree/main/ScanBarcodes_Expo).

## License

You can request a 30-day trial license via the [Request a Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=github&package=mobile) link.

## Support

[https://www.dynamsoft.com/company/contact/](https://www.dynamsoft.com/company/contact/)
