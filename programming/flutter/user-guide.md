---
layout: default-layout
title: Barcode Reader Integration Guide (Ready-To-Use Edition)
description: This is the user guide of Dynamsoft Barcode Reader Flutter SDK (Ready-to-Use Edition).
keywords: user guide, flutter, ready to use, barcode, scanner
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---


#  Barcode Reader Integration Guide (Ready-To-Use Edition)

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

> [!TIP]
> If you are downloading Xcode or Android Studio for the first time, please remember to also install the command-line tools.

> [!NOTE]
> Please note that the sample projects that we offer were last tested with Flutter 3.35.7

## Including the Library

Run the following command in the root directory of your flutter project to add `dynamsoft_barcode_reader_bundle_flutter` to the dependencies:

```bash
flutter pub add dynamsoft_barcode_reader_bundle_flutter
```

Then run the following command to install all the dependencies:

```bash
flutter pub get
```

## Building the Barcode Scanner Widget

Now that the package is added, it's time to start building the `BarcodeScanner` widget.

### Importing the Library

To use the BarcodeScanner API, please import `dynamsoft_barcode_reader_bundle_flutter` in *main.dart*:

```dart
import 'package:dynamsoft_barcode_reader_bundle_flutter/dynamsoft_barcode_reader_bundle_flutter.dart';
```

### Quick Start

The code snippet below shows the simplest implementation of a **function** that will initialize and launch the Barcode Scanner. Please note that in order to use the Barcode Scanner, a **valid license must be defined in the code**.

```dart
import 'package:dynamsoft_barcode_reader_bundle_flutter/dynamsoft_barcode_reader_bundle_flutter.dart';

void _launchBarcodeScanner() async{
  var config = BarcodeScannerConfig(
    license: 'DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9',
  );
  const result = await BarcodeScanner.launch(config);
  if(result.status == EnumResultStatus.finished){
    // handle the result
  }
}
```

The above function can be triggered on any event, like when the app starts, on a button click, or more. Once the barcode scanner is launched, a barcode scanning interface opens - allowing the user to point at any barcode with the phone camera in order to read the barcode(s). Once the scan is complete, the interface closes and the result is returned.

> [!TIP]
> The Barcode Scanner is able to operate in a *single scan* mode or a *multiple scan* mode. In *single scan* mode, the barcode scanner can only capture one barcode at a time, even if there are multiple barcodes in the same frame or within the same view. In order to read multiple barcodes in the same frame or view, the barcode scanner needs to be in *multiple scan* mode. 
> 
> The scanning mode is determined by the `scanningMode` parameter of [`BarcodeScannerConfig`](api-reference/barcode-scanner/barcode-scanner-config.md). To use single scan mode, set `scanningMode` to *single*. To use multiple scan mode, set `scanningMode` to *multiple*.

This next code snippet demonstrates a simple example on how to configure the `_launchBarcodeScanner` function in the full **main.dart** implementation.

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
      scanningMode: 'single', // configuring the Barcode Scanner into single scan mode
    );
    BarcodeScanResult result = await BarcodeScanner.launch(config);
    if(result.status == EnumResultStatus.finished){
      setState(() {
        if (barcodeScanResult.status == EnumResultStatus.canceled) {
          _displayString = "Scan canceled";
        } else if (barcodeScanResult.status == EnumResultStatus.exception) {
          _displayString = "ErrorCode: ${barcodeScanResult.errorCode}\n\nErrorString: ${barcodeScanResult.errorMessage}";
        } else {
          //EnumResultStatus.finished
          if (scanningMode == EnumScanningMode.single) {
            var barcode = barcodeScanResult.barcodes![0];
            _displayString = "Format: ${barcode!.formatString}\nText: ${barcode.text}";
          } else {
            // EnumScanningMode.multiple
            _displayString =
                "Barcodes count: ${barcodeScanResult.barcodes!.length}\n\n"
                "${barcodeScanResult.barcodes!.map((barcode) {
                  return "Format: ${barcode!.formatString}\nText: ${barcode.text}";
                }).join("\n\n")}";
          }
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
const config = BarcodeScannerConfig(
  
  ///The license key required to initialize the BarcodeScanner.
  license: "DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9", //The license string here grants a time-limited free trial which requires network connection to work.
  
  ///Sets the barcode format(s) to read.
  ///This value is a combination of EnumBarcodeFormat flags that determine which barcode types to read.
  ///For example, to scan QR codes and OneD codes,
  ///set the value to `EnumBarcodeFormat.BF_QR_CODE | EnumBarcodeFormat.BF_ONED`.
  barcodeFormats: EnumBarcodeFormat.BF_QR_CODE | EnumBarcodeFormat.BF_ONED,
  
  ///Defines the scanning area as a DSRect object where barcodes will be detected.
  ///Only the barcodes located within this defined region will be processed. 
  ///Default is undefined, which means the full screen will be scanned.
  scanRegion: DSRect(top: 0.25, bottom: 0.75, left: 0.25, right: 0.75, measuredInPercentage: true), // scan the middle 50% of the screen
  
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
  isScanLaserVisible: true,

  ///Sets the scanning mode for the BarcodeScanner.
  ///The mode is defined by the EnumScanningMode and affects the scanning behavior. Default is `EnumScanningMode.single`.
  scanningMode: EnumScanningMode.single,

  ///Defines the expected number of barcodes to be scanned.
  ///The scanning process will automatically stop when the number of detected barcodes reaches this count.
  ///Only available when `scanningMode` is set to `EnumScanningMode.multiple`. Default is 999.
  expectedBarcodesCount: 999,

  ///Specifies the maximum number of consecutive stable frames to process before exiting scanning.
  ///A "stable frame" is one where no new barcode is detected.
  ///Only available when `scanningMode` is set to `EnumScanningMode.multiple`. Default is 10.
  maxConsecutiveStableFramesToExit: 10,

  ///Specifies the template configuration for the BarcodeScanner.
  ///This can be either a file path or a JSON string that defines various scanning parameters.
  ///Default is undefined, which means the default template will be used.
  templateFile: "JSON template string",
);
```

> [!TIP]
> Only a subset of the Barcode Reader parameters is exposed in the BarcodeScannerConfig class. In order to fully customize the performance of the BarcodeScanner instance, then we recommend using a JSON template to set the parameters, and then assign it to the BarcodeScanner instance using the `templateFile` parameter. To learn how to create your own JSON template, please refer to this [page](https://www.dynamsoft.com/barcode-reader/docs/core/programming/features/use-runtimesettings-or-templates.html?lang=objc,swift#json-template).

## Run the Project

### iOS

Before the project can be deployed to a *iOS* device, the camera permissions and the developer signature must first be set. To add the camera permissions to the iOS portion of the app, we recommend first installing the **pods** dependencies to generate the **.xcworkspace** project under the ios folder (`ios/Runner.xcworkspace`). Please run the following commands from the root directory:

```bash
cd ios/
pod install --repo-update
```

Once the pods are installed, *Runner.xcworkspace* should now be generated in the *ios* folder. 

#### Camera Permissions

To add the **camera permissions**, open the generated *Runner.xcworkspace* and navigate to the *Info* section of the project settings. Then you must add the "Privacy - Camera Usage Description" key to the list (where you can also assign a string message to show in the alert box).

#### Deploying to Device

In order to deploy the app to a iOS device, we recommend doing it via Xcode by using the `Runner.xcworkspace` project that was generated when the pods were installed. Since the camera permissions are taken care of, all you need to do is properly configure the *Signing & Capabilities* section of the project settings. Should the iOS device be connected to the computer, you can now run and deploy the app to the device. 

If everything is set up correctly, you should see the app running on your device.

Once the pods are installed, *Runner.xcworkspace* should now be generated in the *ios* folder. To add the camera permissions, open the generated *Runner.xcworkspace* and navigate to the *Info* section of the project settings. Then you must add the "Privacy - Camera Usage Description" key to the list (where you can also assign a string message to show in the alert box).


### Android

#### Camera Permissions

When using the Ready-To-Use BarcodeScanner API, **there is no need to configure the camera permissions for Android via the [`PermissionUtil`]({{ site.dcv_flutter_api }}utility/permission-util.html) class**. That is because the BarcodeScanner API takes care of these permissions internally, saving you the trouble.

#### Deploying to Device

Go to the project folder, open a new terminal and run the following command:

```bash
flutter run -d <DEVICE_ID>
```

You can get the IDs of all connected (physical) devices by running the command `flutter devices`. 

## Full Sample Code

The full sample code is available [here](https://github.com/Dynamsoft/barcode-reader-flutter-samples/tree/main/ScanBarcodes_ReadyToUseComponent).

## License

You can request a 30-day trial license via the [Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=github&package=mobile) portal.

## Support

https://www.dynamsoft.com/company/contact/
