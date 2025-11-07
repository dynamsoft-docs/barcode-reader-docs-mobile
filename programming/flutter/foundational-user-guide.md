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

This guide will help you develop a barcode scanning app using the [Dynamsoft Capture Vision Foundational API]({{ site.dcv_flutter }}).

Dynamsoft Capture Vision (DCV) is an aggregating library for several of Dynamsoft's functional products, including the Dynamsoft Barcode Reader SDK. The [`Capture Vision API`]({{ site.dcv_flutter_api }}) does not come with a pre-built UI or an easy configuration interface like the BarcodeScanner component (see this [guide](user-guide.md)) - but it does provide the user with more parameters to control the barcode reading performance and settings.

## System Requirements

* Latest [Flutter framework](https://flutter.dev/)
* Android: Android SDK (API Level 21+), platforms and developer tools
  * Supported OS: Android 5.0 (API Level 21) and higher
  * Supported ABI: **armeabi-v7a**, **arm64-v8a**, **x86** and **x86_64**
  * Development Environment: Android Studio Meerkat (2024.3.1); Java 17+; Gradle 8.0+
* iOS
  * Supported OS: iOS 13+
  * Supported ABI: **arm64** and **x86_64**
  * Development Environment: Xcode 13+ (Xcode 14.1+ recommended)

> [!TIP]
> If you are downloading Xcode or Android Studio for the first time, please remember to also install the command-line tools.

> [!NOTE]
> Please note that the sample projects that we offer were built and tested with Flutter 3.35.7

## Including the Library

Run the following command in the root directory of your flutter project to add `dynamsoft_barcode_reader_bundle_flutter` to the dependencies:

```bash
flutter pub add dynamsoft_barcode_reader_bundle_flutter
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

- Define a valid license via the [`LicenseManager`]({{ site.dcv_flutter_api }}license/license-manager.html)
- Initialize the [`CameraEnhancer`]({{ site.dce_flutter_api }}camera-enhancer.html) object
- Initialize the [`CaptureVisionRouter`]({{ site.dcv_flutter_api }}capture-vision-router/capture-vision-router.html) object
- Bind the `CameraEnhancer` object to the `CaptureVisionRouter` object
- Register a [`CapturedResultReceiver`]({{ site.dcv_flutter_api }}capture-vision-router/captured-result-receiver.html) object to listen for decoded barcodes via the callback function [`onDecodedBarcodesReceived`]({{ site.dcv_flutter_api }}capture-vision-router/captured-result-receiver.html#ondecodedbarcodesreceived)
- Open the camera
- Start barcode scanning via the [`startCapturing`]({{ site.dcv_flutter_api }}capture-vision-router/capture-vision-router.html#startcapturing) method

The code snippet below shows the simplest implementation that will set up and launch the Barcode Reader. Please note that in order to use the Barcode Reader, a **valid license must be defined in the code**.

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
  final CaptureVisionRouter _cvr = CaptureVisionRouter.instance;
  final CameraEnhancer _camera = CameraEnhancer.instance;
  final String _templateName = EnumPresetTemplate.readBarcodes;
  late final CapturedResultReceiver _receiver = CapturedResultReceiver()
    ..onDecodedBarcodesReceived = (DecodedBarcodesResult result) async {
      if (result.items?.isNotEmpty ?? false) {
        _cvr.stopCapturing(); // stop the camera and the capture process
        var displayString = result.items?.map((item) => "Format: ${item.formatString}\nText: ${item.text}").join('\n\n'); // create a string from the barcode text to be displayed in the alert box
        showTextDialog("Barcodes Count: ${result.items?.length ?? 0}", displayString ?? "", () {
          _cvr.startCapturing(_templateName);
        });
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
> 1. Using the [`SimplifiedBarcodeReaderSettings`](./api-reference/barcode-reader/simplified-barcode-reader-settings.md) class (via the [`SimplifiedCaptureVisionSettings`]({{ site.dcv_flutter_api }}capture-vision-router/simplified-capture-vision-settings.html) class) and the [`updateSettings`]({{ site.dcv_flutter_api }}capture-vision-router/capture-vision-router.html#updatesettings) method.
> 2. Using a JSON template file that contains the algorithm parameters, which is then applied using the [`initSettings`]({{ site.dcv_flutter_api }}capture-vision-router/capture-vision-router.html#initsettings) method.
>
> If you are looking to create a custom JSON settings template, please refer to this [page](https://www.dynamsoft.com/barcode-reader/docs/core/programming/features/use-runtimesettings-or-templates.html?lang=objc,swift#json-template).

### Specify Barcode Formats and Count

One of the main parameters that is available to the Barcode Reader is the `barcodeFormatIds` - which sets what barcode symbologies will be read. Another one of those parameters is the `expectedBarcodesCount` - which specifies how many barcodes are expected to be read in a frame or image. Now let's see the ways we can configure these parameters

#### Using the `SimplifiedCaptureVisionSettings` class

The settings of the Barcode Reader can be configured using the [`SimplifiedBarcodeReaderSettings`](./api-reference/barcode-reader/simplified-barcode-reader-settings.md) class (via [`SimplifiedCaptureVisionSettings`]({{ site.dcv_flutter_api }}capture-vision-router/simplified-capture-vision-settings.html)).

> [!NOTE]
> Please note that as the name implies, `SimplifiedBarcodeReaderSettings` gives the user access to only the basic and most important barcode reader settings. If you would like to utilize the full range of barcode reader settings, please go to the [JSON template section](#using-a-json-template).

Taking the code snippet in the [Quick Start section](#quick-start), we will edit the `initSdk` function to configure the `expectedBarcodesCount` and the `barcodeFormatIds` of the Barcode Reader instance via `SimplifiedCaptureVisionSettings` and `SimplifiedBarcodeReaderSettings`.

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

#### Using a JSON Template

The first thing that we need to do is create the JSON template. Here is a basic JSON template example that configures the `BarcodeFormatIds` and the `ExpectedBarcodesCount`

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

Now that you have the JSON template, it's time to convert it to a JSON string and then use the initSettings method to apply those settings.

```dart
void initSdk() async {
  //...
  _cvr.initSettings("{\"CaptureVisionTemplates\":[{\"Name\":\"CV_0\",\"ImageROIProcessingNameArray\":[\"TA_0\"]}],\"TargetROIDefOptions\":[{\"Name\":\"TA_0\",\"TaskSettingNameArray\":[\"BR_0\"]}],\"BarcodeReaderTaskSettingOptions\":[{\"Name\":\"BR_0\",\"BarcodeFormatIds\":[\"BF_ONED\",\"BF_QR_CODE\"],\"ExpectedBarcodesCount\":0}]}");
  //...
  _cvr_.startCapturing("CV_0"); // since the CaptureVisionTemplate is called CV_0, then that is the template name that should be used with startCapturing
}
```

> [!TIP]
> Once you have the JSON template completed, you must remove all the white spaces and then stringify the content of the JSON template in order to get the JSON string.
> 
> To learn how to create your own JSON template, please refer to this [page](https://www.dynamsoft.com/barcode-reader/docs/core/programming/features/use-runtimesettings-or-templates.html?lang=objc,swift#json-template).

### UI Customization

If you would like to learn more on how to customize the UI, please refer to the [UI Customization](explore-features/ui-customization.md) guide.

### Advanced Features

If you would like to learn about some of the advanced features of the library and how to implement them, please refer to the [Advanced Features](explore-features/advanced-features.md) guide.

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

### Android

#### Camera Permissions

On Android, permission to use the camera must be set in the code as such:

```dart
PermissionUtil.requestCameraPermission();
```

> [!NOTE]
> This is done via the [`PermissionUtil`]({{ site.dcv_flutter_api }}utility/permission-util.html) class. Please note that the code snippets in the previous sections contain this line in order to make the app run successfully.

#### Deploying to Device

Go to the project folder, open a new terminal and run the following command:

```bash
flutter run -d <DEVICE_ID>
```

You can get the IDs of all connected (physical) devices by running the command `flutter devices`. 

## Full Sample Code

The full sample code is available [here](https://github.com/Dynamsoft/barcode-reader-flutter-samples/tree/main/ScanBarcodes_FoundationalAPI).

## License

You can request a 30-day trial license via the [Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=github&package=mobile) portal.

## Support

https://www.dynamsoft.com/company/contact/
