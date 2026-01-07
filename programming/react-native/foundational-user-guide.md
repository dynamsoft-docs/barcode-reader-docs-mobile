---
layout: default-layout
title: Guide (Foundational) - Dynamsoft Barcode Reader React Native
description: This is the user guide of Dynamsoft Barcode Reader React Native SDK (Foundational-API Edition).
keywords: user guide, React Native, Foundational, barcode, scanner
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

#  Build Your Barcode Scanner First App (with Foundational APIs)

This guide will help you develop a fully-customizable barcode scanning app with the Foundational APIs.

## System Requirements

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

## Installation

Run the following commands in the root directory of your react-native project to add the required dependencies:

```bash
# using npm
npm install dynamsoft-capture-vision-react-native
npm install dynamsoft-barcode-reader-bundle-react-native

# OR using Yarn
yarn add dynamsoft-capture-vision-react-native
yarn add dynamsoft-barcode-reader-bundle-react-native
```

Than run the command to install all dependencies:

```bash
# using npm
npm install 

# OR using Yarn
yarn install
```

For iOS, you must install the necessary native frameworks from CocoaPods by running the pod install command as below:

```bash
cd ios
pod install
```

## License Actication

License is configured when launching the `BarcodeScanner` via `BarcodeScanConfig`. For example:

```tsx
const License = 'DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9';
LicenseManager.initLicense(License).catch(e => {
  Alert.alert('License error', e.message);
});
```

> [!Note]
>
> - The LICENSE string here grants a time-limited free trial which requires network connection to work.
> - You can request a 30-day trial license via the [Request a Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=guide&package=mobile){:target="_blank"} link.
> - If you download the <a href="https://www.dynamsoft.com/barcode-reader/downloads/?utm_source=docs#mobile" target="_blank">Installation Package</a>, it comes with a 30-day trial license by default.

## Build Your Barcode Scanner App

### Preparation

1. Initialize a new React Native project with the following command:

    ```bash
    npx @react-native-community/cli init BarcodeScanner
    ```

2. Open the project folder and follow the [installation section](#installation) to install the dependencies.

### Implementing the Barcode Scanner

Find the App.tsx file in your project and replace the file with the following code:

```tsx
import {
  CameraEnhancer,
  CameraView,
  CaptureVisionRouter,
  EnumPresetTemplate,
  LicenseManager,
} from 'dynamsoft-capture-vision-react-native';
import React, {useEffect, useRef} from 'react';
import {Alert, AppState, SafeAreaView, StyleSheet} from 'react-native';

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
    };
  }, [cvr, camera]);

  return (
    <SafeAreaView style={StyleSheet.absoluteFill}>
      <CameraView style={StyleSheet.absoluteFill} ref={cameraView}/>
    </SafeAreaView>
  );
}

export default App;
```

### Run the App

#### Android

Run the following command to start the app:

```bash
# using npm
npm run android

# OR using Yarn
yarn android
```

#### iOS

1. Include the camera permission via `ios/your-project-name/Info.plist` inside the `<dict>` element:

    ```xml
    <key>NSCameraUsageDescription</key>
        <string></string>
    ```

2. Open the workspace via the Xcode.

3. Configure the *Provisioning* and *Signing* settings.

4. Run the app via the Xcode workspace.

## Full Sample Code

The full sample code is available [here](https://github.com/Dynamsoft/barcode-reader-react-native-samples/tree/main/ScanBarcodes_FoundationalAPI).

## License

You can request a 30-day trial license via the [Request Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=github&package=mobile) link.

## Support

[https://www.dynamsoft.com/company/contact/](https://www.dynamsoft.com/company/contact/)
