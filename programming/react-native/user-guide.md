---
layout: default-layout
title: Guide (RTU) - Dynamsoft Barcode Reader React Native
description: This is the user guide of Dynamsoft Barcode Reader React Native SDK (Ready-to-Use Edition).
keywords: user guide, React Native, ready to use, barcode, scanner
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

#  Barcode Reader Integration Guide (Ready-To-Use Edition)

This guide will help you develop a barcode scanning app with the Ready-To-Use (RTU) component [`BarcodeScanner`](api-reference/barcode-scanner/index.md).

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
const LICENSE = 'DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9';
const StartScanning = (): Promise<BarcodeScanResult> => {
  let barcodeScanConfig = {
    license: LICENSE
  } as BarcodeScanConfig;
  return BarcodeScanner.launch(barcodeScanConfig);
};
```

> [!Note]
>
> - The LICENSE string here grants a time-limited free trial which requires network connection to work.
> - You can request a 30-day trial license via the [Request a Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=guide&package=react-native){:target="_blank"} link.
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
import React, {useState} from 'react';
import {Button, ScrollView, StyleSheet, Text, View} from 'react-native';
import {
  BarcodeScanConfig,
  BarcodeScanner,
  BarcodeScanResult,
  EnumResultStatus,
  EnumScanningMode,
} from 'dynamsoft-barcode-reader-bundle-react-native';

const LICENSE = 'DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9';
const StartScanning = (): Promise<BarcodeScanResult> => {
  let barcodeScanConfig = {
    license: LICENSE,
    scanningMode: EnumScanningMode.SM_SINGLE,
  } as BarcodeScanConfig;
  return BarcodeScanner.launch(barcodeScanConfig);
};

const BarcodeScanResultToDisplayString = (barcodeResult: BarcodeScanResult) => {
  let displayString: string;
  if (barcodeResult.resultStatus === EnumResultStatus.RS_FINISHED) {
    let barcode = barcodeResult?.barcodes![0];
    displayString = `${barcode.formatString}: ${barcode.text}`;
  } else if (barcodeResult.resultStatus === EnumResultStatus.RS_CANCELED) {
    displayString = 'Scan cancelled.';
  } else {
    displayString = `ErrorCode: ${barcodeResult.errorCode}\n\nErrorMessage: ${barcodeResult.errorString}`;
  }
  return displayString;
};


function App(): React.JSX.Element {
  const [display, setDisplay] = useState({text: '', isError: false});

  const scanBarcode = async () => {
    let barcodeResult: BarcodeScanResult;
    barcodeResult = await StartScanning();
    let displayString = BarcodeScanResultToDisplayString(barcodeResult);
    setDisplay({text: displayString, isError: barcodeResult.resultStatus === EnumResultStatus.RS_EXCEPTION})
  };

  return (
    <View style={styles.container}>
      <ScrollView>
        <Text style={[styles.text, display.isError ? styles.error : null]}>
          {display.text}
        </Text>
      </ScrollView>
      <View style={styles.spacer}/>
      <Button title={'Start Scanning'} onPress={() => scanBarcode()}/>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    alignItems: 'center',
    justifyContent: 'center',
    padding: 20,
    marginBottom: 50,
  },
  text: {marginTop: 20, fontSize: 16, color: 'black'},
  error: {color: 'red'},
  spacer: {height: 20},
});

export default App;
```

### (Optional) Configure Your Barcode Scanner

You can configure the `BarcodeScanner` by setting the following properties in the `BarcodeScanConfig` object:

```tsx
  let barcodeScanConfig = {
    license: LICENSE,
    scanningMode: EnumScanningMode.SM_SINGLE,
    /** Set the supported barcode format.*/
    barcodeFormats: EnumBarcodeFormat.BF_QR_CODE | EnumBarcodeFormat.BF_ONED,
    /** Restrict the scan region.*/
    scanRegion: {top: 0.35, bottom: 0.65, left: 0.15, right: 0.85, measuredInPercentage: true}, 
    /** Set to true to display the torch button, enabling users to turn the flashlight on/off. Default is true.*/
    isTorchButtonVisible: true,
    /** Enable the beep sound, or false to disable it. Default is false. */
    isBeepEnabled: false,
    /** Enable the vibration, or false to disable it. Default is false. */
    isVibrateEnabled: false,
    /** Automatically zoom in to improve barcode detection. Default is false. */
    isAutoZoomEnabled: false,
    /** This button allows users to exit the scanning interface. Default is true. */
    isCloseButtonVisible: true,
    /** This button lets users switch between available cameras (e.g., front and rear). Default is false. */
    isCameraToggleButtonVisible: false,
    /** A scanning laser overlay on the scanning screen. Default is true. */
    isScanLaserVisible: true,
  } as BarcodeScanConfig;
```

View all available [BarcodeScanConfig properties](api-reference/barcode-scanner/barcode-scanner-config.md).

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

The full sample code is available [here](https://github.com/Dynamsoft/barcode-reader-react-native-samples/tree/main/ScanBarcodes_ReadyToUseComponent).

## License

You can request a 30-day trial license via the [Request a Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=github&package=mobile) link.

## Support

[https://www.dynamsoft.com/company/contact/](https://www.dynamsoft.com/company/contact/)
