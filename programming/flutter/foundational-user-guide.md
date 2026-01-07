---
layout: default-layout
title: Guide (Foundational) - Dynamsoft Barcode Reader Flutter
description: This is the user guide of Dynamsoft Barcode Reader Flutter SDK (Foundational Edition).
keywords: user guide, flutter, ready to use, barcode, scanner
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Barcode Reader Integration Guide (Foundational Edition)

This guide walks you through building a barcode scanning app using the [Dynamsoft Capture Vision Foundational API]({{ site.dcv_flutter_api }}).

The Foundational API provides full control over barcode scanning performance and settings. Unlike the Ready-To-Use BarcodeScanner component ([guide](user-guide.md)), you'll build your own UI and configure the scanning workflow using the [`CaptureVisionRouter`]({{ site.dcv_flutter_api }}capture-vision-router/capture-vision-router.html) and [`CameraEnhancer`]({{ site.dce_flutter_api }}camera-enhancer.html) APIs.

## System Requirements

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

> [!NOTE]
> Adding `dynamsoft_barcode_reader_bundle_flutter` automatically includes `dynamsoft_capture_vision_flutter`, which is the library you'll interact with directly.

## Building the Barcode Reader

### Configure the `main.dart`

Replace your **main.dart** with the following code:

```dart
import 'package:flutter/material.dart';
import 'package:dynamsoft_capture_vision_flutter/dynamsoft_capture_vision_flutter.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  // This widget is the root of your application.
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'ScanBarcodes',
      theme: ThemeData(colorScheme: ColorScheme.fromSeed(seedColor: Colors.orange)),
      home: const MyHomePage(title: 'ScanBarcodes'),
    );
  }
}

class MyHomePage extends StatefulWidget {
  final String title;

  const MyHomePage({super.key});

  @override
  State<MyHomePage> createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  // Create the CaptureVisionRouter instance. The CaptureVisionRouter is the class for managing the barcode scanning process.
  final CaptureVisionRouter _cvr = CaptureVisionRouter.instance;
  // Create the camera instance
  final CameraEnhancer _camera = CameraEnhancer.instance;
  final String _templateName = EnumPresetTemplate.readBarcodes;
  // Define the result receiver for receiving the captured results.
  late final CapturedResultReceiver _receiver = CapturedResultReceiver()
    ..onDecodedBarcodesReceived = (DecodedBarcodesResult result) async {
      if (result.items?.isNotEmpty ?? false) {
        // Stop capturing when dealing with the results.
        _cvr.stopCapturing();
        var displayString = result.items?.map((item) => "Format: ${item.formatString}\nText: ${item.text}").join('\n\n');
        showTextDialog("Barcodes Count: ${result.items?.length ?? 0}", displayString ?? "", () {
          _cvr.startCapturing(_templateName);
        });
      }
    };

  @override
  void initState() {
    super.initState();
    // Request camera permission
    PermissionUtil.requestCameraPermission();
    // A valid license is required.
    LicenseManager.initLicense('DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9').then((data) {
      final (isSuccess, message) = data;
      if (!isSuccess) {
        print("license error: $message");
      }
    });
    initSdk();
  }

  void initSdk() async {
    // Bind the Camera instance with the CaptureVisionRouter instance.
    await _cvr.setInput(_camera);
    // Bind the result receiver with the CaptureVisionRouter instance.
    _cvr.addResultReceiver(_receiver);
    // Open the camera
    _camera.open();
    try {
      // Start the capturing process.
      await _cvr.startCapturing(_templateName);
    } catch (e) {
      showTextDialog("StartCapturing Error", e.toString(), null);
    }
  }

  void showTextDialog(String title, String message, VoidCallback? onDismiss) {
    showDialog(
      context: context,
      builder: (BuildContext context) {
        return AlertDialog(title: Text(title), content: Text(message));
      },
    ).then((_) {
      //Callback when dialog dismissed
      onDismiss?.call();
    });
  }

  @override
  void dispose() {
    super.dispose();
    // Stop capturing, close the camera, and remove the result receiver when disposing.
    _cvr.stopCapturing();
    _camera.close();
    _cvr.removeResultReceiver(_receiver);
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(backgroundColor: Theme.of(context).colorScheme.inversePrimary, title: Text(widget.title)),
      body: Center(child: CameraView(cameraEnhancer: _camera)),
    );
  }
}
```

> [!NOTE]
>
>- The license string here grants a time-limited free trial which requires network connection to work.
>- You can request a 30-day trial license via the [Request a Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=guide&package=flutter){:target="_blank"} link.

Related APIs:

- [`LicenseManager`]({{ site.dcv_flutter_api }}license/license-manager.html) - licensing.
- [`CameraEnhancer`]({{ site.dce_flutter_api }}camera-enhancer.html) - camera operations
- [`CaptureVisionRouter`]({{ site.dcv_flutter_api }}capture-vision-router/capture-vision-router.html) - manages the scanning workflow
- [`CapturedResultReceiver`]({{ site.dcv_flutter_api }}capture-vision-router/captured-result-receiver.html) - receives processed results

### Customize the Barcode Reader (Optional)

Although the default barcode reader template is optimized for common scenarios, you may customize performance or behavior as needed.

#### Specify Barcode Formats and Count

You can configure which barcode formats to read and how many barcodes to expect per frame.

##### Option 1. Using SimplifiedCaptureVisionSettings

Configure basic settings using the [`SimplifiedBarcodeReaderSettings`](./api-reference/barcode-reader/simplified-barcode-reader-settings.md) class:

```dart
void initSdk() async {
  //...
  SimplifiedCaptureVisionSettings? settings =  await _cvr.getSimplifiedSettings(_templateName);

  // Set the expected barcode count to 0 when you are not sure how many barcodes you are scanning.
  // Set the expected barcode count to 1 can maximize the barcode decoding speed.
  settings.barcodeSettings!.expectedBarcodesCount = 0;
  
  // set the barcode formats to just oned and qrCode so that the library only picks up those two types
  settings.barcodeSettings!.barcodeFormatIds = EnumBarcodeFormat.oned |EnumBarcodeFormat.qrCode;
  
  _cvr.updateSettings(settings, _templateName);
  _cvr.startCapturing(_templateName);
  //...
}
```

##### Option 2. Using a JSON Template

For advanced customization, create a JSON template that configures the barcode reader parameters:

```json
{
    "CaptureVisionTemplates": [
        {
            "Name" : "CV_0",
            "ImageROIProcessingNameArray": ["TA_0" ]
        }
    ],
    "TargetROIDefOptions" : [
        {
            "Name" : "TA_0",
            "TaskSettingNameArray": [ "BR_0" ]
        }
    ],
    "BarcodeReaderTaskSettingOptions": [
        {
            "Name" : "BR_0",
            "BarcodeFormatIds" : ["BF_ONED", "BF_QR_CODE"],
            "ExpectedBarcodesCount": 0
        }
    ]
}
```

Apply the JSON template using the `initSettings` method:

```dart
void initSdk() async {
  //...
  _cvr.initSettings("{\"CaptureVisionTemplates\":[{\"Name\":\"CV_0\",\"ImageROIProcessingNameArray\":[\"TA_0\"]}],\"TargetROIDefOptions\":[{\"Name\":\"TA_0\",\"TaskSettingNameArray\":[\"BR_0\"]}],\"BarcodeReaderTaskSettingOptions\":[{\"Name\":\"BR_0\",\"BarcodeFormatIds\":[\"BF_ONED\",\"BF_QR_CODE\"],\"ExpectedBarcodesCount\":0}]}");
  //...
  _cvr.startCapturing("CV_0"); // Use the template name defined in the JSON
}
```

> [!TIP]
> Once you have the JSON template completed, you must remove all the white spaces and then stringify the content of the JSON template in order to get the JSON string.
> 
> To learn how to create your own JSON template, please refer to this [page](https://www.dynamsoft.com/barcode-reader/docs/core/programming/features/use-runtimesettings-or-templates.html?lang=objc,swift#json-template).

#### Specify the Scan Region

Restricting the scan region can reduce processing time and avoid reading unwanted areas:

```dart
void initSdk() async {
  final scanRegion = DSRect(left: 0.1, top: 0.4, right: 0.9, bottom: 0.6, measuredInPercentage: true);
  _camera.setScanRegion(scanRegion);
}
```

#### Additional Customization

For more advanced customization options:

- [UI Customization](explore-features/ui-customization.md) - Customize the camera view and overlay
- [Advanced Features](explore-features/advanced-features.md) - Explore advanced barcode reading features

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

The full sample code is available [here](https://github.com/Dynamsoft/barcode-reader-flutter-samples/tree/main/ScanBarcodes_FoundationalAPI).

## License

You can request a 30-day trial license via the [Request a Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=guide&package=mobile){:target="_blank"} link.

## Support

[https://www.dynamsoft.com/company/contact/](https://www.dynamsoft.com/company/contact/)
