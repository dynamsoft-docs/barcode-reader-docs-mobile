---
layout: default-layout
title: Guide (RTU) - Dynamsoft Barcode Reader Flutter
description: This is the user guide of Dynamsoft Barcode Reader Flutter SDK (Ready-to-Use Edition).
keywords: user guide, flutter, ready to use, barcode, scanner
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---


# Build Your Barcode Scanning APP (with Ready-To-Use Component)

This guide will help you develop a barcode scanning app with the [`BarcodeScanner`](api-reference/barcode-scanner/index.md) Ready-To-Use (RTU) component.

The `BarcodeScanner` is a ready-to-use component that allows developers to quickly and seamlessly integrate barcode scanning into an application without needing to worry about the UI, allowing the developer to focus on other aspects of the application.

Even though the UI comes with a default look, the [`BarcodeScanner` API](api-reference/barcode-scanner/barcode-scanner.md) provides the developer with customization options for the UI as well as control over the barcode scanning performance via a set of the basic parameters of barcode decoding that the library offers.

## Requirements

* Latest [Flutter SDK](https://flutter.dev/)
* Android: Android SDK (API Level 21+), platforms and developer tools
  * Supported OS: Android 5.0 (API Level 21) and higher
  * Supported ABI: armeabi-v7a, arm64-v8a, x86 and x86_64
  * Development Environment: Android Studio Meerkat (2024.3.1); Java 17+; Gradle 8.0+
* iOS
  * Supported OS: iOS 13+
  * Supported ABI: arm64 and x86_64
  * Development Environment: Xcode 13+ (Xcode 14.1+ recommended)

## Adding the Library

Run the following in your project root:

```bash
flutter pub add dynamsoft_barcode_reader_bundle_flutter
flutter pub get
```

## Building the Barcode Scanner

Now that the package is added, it's time to start building the `BarcodeScanner` widget.

### Quick Start

Replace your **main.dart** with the following code:

```dart
import 'package:flutter/material.dart';
import 'package:dynamsoft_barcode_reader_bundle_flutter/dynamsoft_barcode_reader_bundle_flutter.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  // This widget is the root of your application.
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Scan Barcodes RTU',
      theme: ThemeData(colorScheme: ColorScheme.fromSeed(seedColor: Colors.orange)),
      home: const MyHomePage(title: 'Scan Barcodes RTU'),
    );
  }
}

class MyHomePage extends StatefulWidget {
  final String title;
  const MyHomePage({super.key, required this.title});
  @override
  State<MyHomePage> createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  String _displayString = ""; // used to show the barcode result
  void _launchBarcodeScanner() async{
    var config = BarcodeScannerConfig(
      license: 'DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9',
      /// You can switch between single & multiple here.
      /// Single mode can scan multiple barcodes at once but only returns one result.
      /// Multiple mode returns multiple results.
      scanningMode: EnumScanningMode.single,
    );
    BarcodeScanResult result = await BarcodeScanner.launch(config);

    if(result.status == EnumResultStatus.finished){
      setState(() {
        if (result.status == EnumResultStatus.canceled) {
          _displayString = "Scan canceled";
        } else if (result.status == EnumResultStatus.exception) {
          _displayString = "ErrorCode: ${result.errorCode}\n\nErrorString: ${result.errorMessage}";
        } else {
          var barcode = result.barcodes![0];
          _displayString = "Format: ${barcode!.formatString}\nText: ${barcode.text}";
        }
      });
    }
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
            appBar: AppBar(title: Text(widget.title)),
            body: Center(
              child: Column(
                mainAxisAlignment: MainAxisAlignment.center,
                children: <Widget>[
                  TextButton(
                    onPressed: _launchBarcodeScanner,
                    child: const Text("Scan Barcodes"),
                  ),
                  SizedBox(height: 20),
                  Padding(
                    padding: EdgeInsets.symmetric(horizontal: 20),
                    child: Text(_displayString, style: Theme.of(context).textTheme.bodyLarge),
                  ),
                ],
              ),
            )
    );
  }
}
```

> [!NOTE]
>- The license string here grants a time-limited free trial which requires network connection to work.
>- You can request a 30-day trial license via the [Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=guide&package=mobile) portal.
>- The barcode result is displayed in a text label that is set by the `_displayString` variable.

### Barcode Scan Result

Also see it in the [BarcodeScanResult](api-reference/barcode-scanner/barcode-scan-result.md) section of API References.

`BarcodeScanResult` structure:
- resultStatus: The status of the barcode result, of type `EnumResultStatus`.
  - finished: The barcode scan was successful.
  - canceled: The barcode scanning activity is closed before the process is finished.
  - exception: Failed to start barcode scanning or an error occurs when scanning the barcodes.
- errorCode: The error code indicates if something went wrong during the barcode scanning process (0 means no error).
- errorString: The error message associated with the error code if an error occurs during barcode scanning process.
- barcodes: An array of `BarcodeResultItem`.

### Configuring the BarcodeScanner (Optional)

The advantage of using the BarcodeScanner component is in the simplicity of its configuration. As we have shown above, it doesn't take much to get the BarcodeScanner up and running. However, there could be cases where you want to make some changes to the default UI or setup that the BarcodeScanner provides. In this section, we run through the different configuration options provided in the [BarcodeScannerConfig](api-reference/barcode-scanner/barcode-scanner-config.md) class.

```dart
var config = BarcodeScannerConfig(
  license: 'DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9',
  scanningMode: EnumScanningMode.single,
  ///Defines the barcode formats.
  ///For example: set the target barcode formats to OneD and QR.
  /// You have to 'package:dynamsoft_capture_vision_flutter/dynamsoft_capture_vision_flutter.dart' to use the EnumBarcodeFormat.
  barcodeFormats: EnumBarcodeFormat.oned | EnumBarcodeFormat.qrCode,
  ///Defines the scanning area as a DSRect object where barcodes will be detected.
  ///Only the barcodes located within this defined region will be processed. 
  ///Default is undefined, which means the full screen will be scanned.
  scanRegion: DSRect(top: 0.35, bottom: 0.65, left: 0.15, right: 0.85, measuredInPercentage: true),
  ///Determines whether the torch (flashlight) button is visible in the scanning UI.
  ///Set to true to display the torch button, enabling users to turn the flashlight on/off. Default is true.
  isTorchButtonVisible: true,
  ///Specifies if a beep sound should be played when a barcode is successfully detected.
  ///Set to true to enable the beep sound, or false to disable it. Default is false.
  isBeepEnabled: false,
  ///Enables or disables the auto-zoom feature during scanning.
  ///When enabled (true), the scanner will automatically zoom in to improve barcode detection. Default is false.
  isAutoZoomEnabled: false,
  ///Determines whether the close button is visible on the scanner UI.
  ///This button allows users to exit the scanning interface. Default is true.
  isCloseButtonVisible: true,
  ///Specifies whether the camera toggle button is displayed.
  ///This button lets users switch between available cameras (e.g., front and rear). Default is false.
  isCameraToggleButtonVisible: false,
  ///Determines if a scanning laser overlay is shown on the scanning screen.
  ///This visual aid (scan laser) helps indicate the scanning line during barcode detection. Default is true.
  isScanLaserVisible: true
);
```

> [!TIP]
> Only a subset of the Barcode Reader parameters is exposed in the `BarcodeScannerConfig` class. In order to fully customize the performance of the BarcodeScanner instance, then we recommend using a JSON template to set the parameters, and then assign it to the BarcodeScanner instance using the `templateFile` parameter. To learn how to create your own JSON template, please refer to this [page](https://www.dynamsoft.com/barcode-reader/docs/core/programming/features/use-runtimesettings-or-templates.html?lang=objc,swift#json-template).

## Run the Project

### iOS

1. Install CocoaPods dependencies

   Before the project can be deployed to an iOS device, the camera permissions and the developer signature must first be set. To add the camera permissions to the iOS portion of the app, we recommend first installing the **pods** dependencies to generate the **.xcworkspace** project under the ios folder (`ios/Runner.xcworkspace`). Please run the following commands from the root directory:

   ```bash
   cd ios/
   pod install --repo-update
   ```

2. Configure the project in Xcode

   Open Runner.xcworkspace in Xcode and:

   - Add **Privacy – Camera Usage Description** under **Project → Info**
   - Configure **Signing & Capabilities**
   - Connect your device and run the project

### Android

Run the app:

```bash
flutter run
```

Run on a specific device:

```bash
flutter run -d <DEVICE_ID>
```

List devices:

```bash
flutter devices
``` 

## Full Sample Code

The full sample code is available [here](https://github.com/Dynamsoft/barcode-reader-flutter-samples/tree/main/ScanBarcodes_ReadyToUseComponent).

## License

You can request a 30-day trial license via the [Request a Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=guide&package=mobile){:target="_blank"} link.

## Support

[https://www.dynamsoft.com/company/contact/](https://www.dynamsoft.com/company/contact/)
