---
layout: default-layout
title: Barcode Reader Integration Guide (Foundational Edition)
description: This is the user guide of Dynamsoft Barcode Reader Flutter SDK (Foundational Edition).
keywords: user guide, flutter, ready to use, barcode, scanner
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Barcode Reader Integration Guide (Foundational Edition)

This guide will help you develop a barcode scanning app using the [Dynamsoft Capture Vision Foundational API](./api-reference/capture-vision-router-lite/capture-vision-router.md).

Dynamsoft Capture Vision (DCV) is an aggregating library for several of Dynamsoft's functional products, including the Dynamsoft Barcode Reader SDK. The [`Capture Vision API`](./api-reference/capture-vision-router-lite/capture-vision-router.md) does not come with a pre-built UI like the BarcodeScanner component (see this [guide](user-guide.md)) - it does provide the user with more parameters to control the barcode reading performance and settings.

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

> [!TIP]
> If you are downloading Xcode or Android Studio for the first time, please remember to also install the command-line tools.

## Including the Library

Run the following command in the root directory of your flutter project to add `dynamsoft_capture_vision_flutter` to the dependencies:

```bash
flutter pub add dynamsoft_capture_vision_flutter
```

Then run the following command to install all the dependencies:
   
```bash
flutter pub get
```

## Building the Barcode Reader Widget

Now that the package is added, it's time to start building the Barcode Reader widget.

### Importing the Library

To use the Capture Vision API, please import `dynamsoft_capture_vision_flutter` in *main.dart*:

```dart
import 'package:dynamsoft_capture_vision_flutter/dynamsoft_capture_vision_flutter.dart';
```

### Quick Start

In order to implement the full barcode reader workflow, the following needs to be done in order:

- Define a valid license via the [`LicenseManager`](./api-reference/capture-vision-router-lite/license-manager.md)
- Initialize the [`CameraEnhancer`](./api-reference/capture-vision-router-lite/camera-enhancer.md) object
- Initialize the [`CaptureVisionRouter`](./api-reference/capture-vision-router-lite/capture-vision-router.md) object
- Bind the `CameraEnhancer` object to the `CaptureVisionRouter` object
- Register a [`CapturedResultReceiver`](./api-reference/capture-vision-router-lite/captured-result-receiver.md) object to listen for decoded barcodes via the callback function [`onDecodedBarcodesReceived`](./api-reference/capture-vision-router-lite/captured-result-receiver.md#ondecodedbarcodesreceived)
- Open the camera
- Start barcode scanning via the [`startCapturing`](./api-reference/capture-vision-router-lite/capture-vision-router.md#startcapturing) method

The code snippet below shows the simplest implementation that will set up and launch the Barcode Reader. Please note that in order to use the Barcode Reader, a **valid license must be defined in the code**.

```dart
import 'package:dynamsoft_capture_vision_flutter/dynamsoft_capture_vision_flutter.dart';
import 'package:flutter/material.dart';

class MyHomePage extends StatefulWidget {
  const MyHomePage({super.key});

  @override
  State<MyHomePage> createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  final CaptureVisionRouter _cvr = CaptureVisionRouter.instance;
  final CameraEnhancer _camera = CameraEnhancer.instance;
  final String _templateName = EnumPresetTemplate.readBarcodes;
  late final CapturedResultReceiver _receiver = CapturedResultReceiver()
    ..onDecodedBarcodesReceived = (DecodedBarcodesResult result) async {
      if (result.items?.isNotEmpty ?? false) {
        // assign the barcode 
        var displayString = result.items?.map((item) => "Format: ${item.formatString}\nText: ${item.text}").join('\n\n');
        showTextDialog("Barcodes Count: ${result.items?.length ?? 0}", displayString ?? "", () {
        _cvr.startCapturing(_templateName);
      }
    };

  @override
  void initState() {
    super.initState();
    PermissionUtil.requestCameraPermission();
    LicenseManager.initLicense('DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9').then((data) {
      final (isSuccess, message) = data;
      if (!isSuccess) {
        print("license error: $message");
      }
    });
    initSdk();
  }

  void initSdk() async {
    await _cvr.setInput(_camera); //bind CameraEnhancer and CaptureVisonRouter
    _cvr.addResultReceiver(_receiver); //Register `CapturedResultReceiver` object to listen for parsed decoded barcodes result
    _camera.open();
    try {
      await _cvr.startCapturing(_templateName); //Start capturing
    } catch (e) {
      print(e);
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
    _cvr.stopCapturing();
    _camera.close();
    _cvr.removeResultReceiver(_receiver);
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(backgroundColor: Theme.of(context).colorScheme.inversePrimary, title: Text(widget.title)),
      body: Center(child: CameraView(cameraEnhancer: _camera)), // Bind CameraView and CameraEnhancer
    );
  }
}
```

> [!NOTE]
>
>- The license string here grants a time-limited free trial which requires network connection to work.
>- You can request a 30-day trial license via the [Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=guide&package=mobile) portal.

## Configuring the Barcode Reader (Optional)

The Barcode Reader library comes with many customization parameters that can affect the performance of the SDK. Whether you are looking speed up the scan process or increase the read rate when reading a batch of barcodes at once, these parameters can prove to be quite useful in making the Barcode Reader adapt to any kind of situation that it is put in.

> [!TIP]
> The Barcode Reader settings can be changed in two ways:
> 1. Using the [`SimplifiedBarcodeReaderSettings`](./api-reference/capture-vision-router-lite/simplified-barcode-reader-settings.md) class (via the [`SimplifiedCaptureVisionSettings`](./api-reference/capture-vision-router-lite/simplified-capture-vision-settings.md) class) and the [`updateSettings`](./api-reference/capture-vision-router-lite/capture-vision-router.md#updatesettings) method.
> 2. Using a JSON template file that contains the algorithm parameters, which is then applied using the [`initSettings`](./api-reference/capture-vision-router-lite/capture-vision-router.md#initsettings) method.
>
> If you are looking to create a custom JSON settings template, please refer to this [page](https://www.dynamsoft.com/barcode-reader/docs/core/programming/features/use-runtimesettings-or-templates.html?lang=objc,swift#json-template).

### Specify Barcode Formats and Count

One of the main parameters that is available to the Barcode Reader is the `barcodeFormatIds` - which sets what barcode symbologies will be read. Another one of those parameters is the `expectedBarcodesCount` - which specifies how many barcodes are expected to be read in a frame or image. Now let's see the ways we can configure these parameters

#### Using `SimplifiedCaptureVisionSettings`

```dart
import 'package:dynamsoft_capture_vision_flutter/dynamsoft_capture_vision_flutter.dart';

final _cvr = CaptureVisionRouter.instance;
final _templateName = EnumPresetTemplate.readBarcodes; //"ReadBarcodes_Default"

void initSdk() async {
  //...
  SimplifiedCaptureVisionSettings? settings =  await _cvr.getSimplifiedSettings(_templateName);
  settings!.timeout = 1000; // set timeout to 1 second for each frame scan

  // Set the expected barcode count to 0 when you are not sure how many barcodes you are scanning.
  // Set the expected barcode count to 1 can maximize the barcode decoding speed.
  settings.barcodeSettings!.expectedBarcodesCount = 0;
  
  settings.barcodeSettings!.barcodeFormatIds = EnumBarcodeFormat.oned |EnumBarcodeFormat.qrCode | EnumBarcodeFormat.pdf417 | EnumBarcodeFormat.datamatrix;
  //In this case, only timeout, expectedBarcodesCount and barcodeFormatIds will be updated and undefined properties will retain their original values.
  _cvr.updateSettings(settings, _templateName);
  _cvr.startCapturing(_templateName);
  //...
}
```

#### Using a JSON Template

```dart
import 'package:dynamsoft_capture_vision_flutter/dynamsoft_capture_vision_flutter.dart';
final _cvr = CaptureVisionRouter.instance;

void initSettings() async {
  //...
  _cvr.initSettings("{the JSON template as a raw JSON string}");
  //...
  router.startCapturing("{your template name in the template String}");
}
```

> [!NOTE]
> To learn how to create your own JSON template, please refer to this [page](https://www.dynamsoft.com/barcode-reader/docs/core/programming/features/use-runtimesettings-or-templates.html?lang=objc,swift#json-template).

### UI Customization

If you would like to learn more on how to customize the UI, please refer to the [UI Customization](explore-features/ui-customization.md) guide.

### Enabling Haptic Feedback

Another feature that the Barcode Reader library offers is the ability to trigger a couple of haptic feedback reactions once a barcode is found. This is done via the [`FeedBack`](api-reference/capture-vision-router-lite/feedback.md) class - and it should be called in the result callback function so that the haptic feedback occurs once a barcode is successfully decoded.

> [!NOTE]
> To see how the FeedBack class should be implemented to trigger these haptic feedback reactions once a barcode is found, please visit the [`FeedBack` API](api-reference/capture-vision-router-lite/feedback.md) page.

## Run the Project

### Camera Permissions

#### iOS

Before the project can be deployed to a *iOS* device, the camera permissions and the developer signature must first be set. To add the camera permissions to the iOS portion of the app, we recommend first installing the **pods** dependencies to generate the **.xcworkspace** project under the ios folder (`ios/Runner.xcworkspace`). Please run the following commands from the root directory:

```bash
cd ios/
pod install --repo-update
```

Once the pods are installed, *Runner.xcworkspace* should now be generated in the *ios* folder. To add the camera permissions, open the generated *Runner.xcworkspace* and navigate to the *Info* section of the project settings. Then you must add the "Privacy - Camera Usage Description" key to the list (where you can also assign a string message to show in the alert box).

#### Android

On Android, permission to use the camera must be set in the code as such:

```dart
import 'package:dynamsoft_capture_vision_flutter/dynamsoft_capture_vision_flutter.dart';

PermissionUtil.requestCameraPermission();
```

> [!NOTE]
> Please note that the code snippets in the previous sections contain this line in order to make the app run successfully.

### Deploying to Device

#### Android

Go to the project folder, open a new terminal and run the following command:

```bash
flutter run -d <DEVICE_ID>
```

You can get the IDs of all connected (physical) devices by running the command `flutter devices`.

#### iOS

In order to deploy the app to a iOS device, we recommend doing it via Xcode by using the `Runner.xcworkspace` project that was generated when the pods were installed. Since the camera permissions are taken care of, all you need to do is properly configure the *Signing & Capabilities* section of the project settings. Should the iOS device be connected to the computer, you can now run and deploy the app to the device. 

If everything is set up correctly, you should see the app running on your device.

## Full Sample Code

The full sample code is available [here](https://github.com/Dynamsoft/barcode-reader-flutter-samples/tree/main/ScanBarcodes_FoundationalAPI).

## License

You can request a 30-day trial license via the [Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=github&package=mobile) portal.

## Support

https://www.dynamsoft.com/company/contact/
