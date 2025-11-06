---
layout: default-layout
title: Driver License Scanner Integration Guide 
description: This is the user guide of Driver License Scanner Flutter Edition.
keywords: user guide, flutter, foundational, barcode, scanner, driver license, reader
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Driver License Scanner Integration Guide

This guide will focus on the specific use case of scanning driver licenses to quickly retrieve one's ID info. Similar to the [Foundational Integration Guide](foundational-user-guide.md), this guide will utilize the [`Capture Vision Foundational API`]({{ site.dcv_flutter_api }}) to get the driver license scanner up and running.

> [!NOTE]
> The Driver License Scanner is composed of two foundational Dynamsoft products - the [Dynamsoft Barcode Reader](https://www.dynamsoft.com/barcode-reader/sdk-mobile/) and the Dynamsoft Code Parser. The Barcode Reader is responsible for capturing and decoding the PDF417 barcodes of the driver licenses. Afterwards, the barcode result needs to be parsed into human-readable fields, which is where the Code Parser comes into play.

## Supported Driver License Types

Driver licenses come with a PDF417 barcode (usually on the back) that encodes the holder's information. These driver licenses can come in different formats, which means different ways that the information is encoded into the barcode, or even the type of information that is encoded.

### AAMVA Driver License

AAMVA - the American Association of Motor Vehicle Administrators - defines the standard that the majority of North American driver licenses need to adhere to. You can learn more about AAMVA on their [website](https://www.aamva.org/).

All versions of the AAMVA DL/ID specification (2000, 2003, 2005, 2009, 2010, 2011, 2012, 2013, 2016) are supported by the Dynamsoft Barcode Reader.

### South Africa Driver License

Support for South African driver licenses is limited - which means that the library is able to extract only a portion of the personal info that is encoded onto the driver license. Parsing of the full info from the driver license will come in a future version of the library.

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

> [!NOTE]
> Including the `dynamsoft_barcode_reader_bundle_flutter` library will also include the `dynamsoft_capture_vision_flutter` library, which will be the one that is actually imported and used.

## Building the Driver License Scanner Widget

Now that the package is added, it's time to start building the Driver License Scanner widget. Unlike the default implementation of the Barcode Reader that is explored in the other guides, building the driver license scanner requires a few more steps and classes to be implemented to fully represent the parsed result that is produced by the library.

These steps include importing the library, implementing the scanner page, creating the *DriverLicenseScanResult* class, and then putting them all together in `main.dart`.

### Importing the Library

To use the Capture Vision API, please import `dynamsoft_capture_vision_flutter` into the three files that we will be implementing (`main.dart`/`scan_page.dart`/`driver_license_scan_result.dart`):

```dart
import 'package:dynamsoft_capture_vision_flutter/dynamsoft_capture_vision_flutter.dart';
```

### Implementing the Widget

Let's tackle the first and main component, the `ScannerPage` class which will be implemented in `scan_page.dart`. In order to implement the full driver license scanner workflow, the following needs to be done in order:

- Define a valid license via the [`LicenseManager`]({{ site.dcv_flutter_api }}license/license-manager.html)
- Initialize the [`CameraEnhancer`]({{ site.dce_flutter_api }}camera-enhancer.html) object
- Initialize the [`CaptureVisionRouter`]({{ site.dcv_flutter_api }}capture-vision-router/capture-vision-router.html) object
- Bind the `CameraEnhancer` object to the `CaptureVisionRouter` object
- Register a [`CapturedResultReceiver`]({{ site.dcv_flutter_api }}capture-vision-router/captured-result-receiver.html) object to listen for parsed driver license barcode results via the callback function [`onParsedResultsReceived`]({{ site.dcv_flutter_api }}capture-vision-router/captured-result-receiver.html#onparsedresultsreceived) 
- Open the camera
- Start scanning via the [`startCapturing`]({{ site.dcv_flutter_api }}capture-vision-router/capture-vision-router.html#startcapturing) method while being configured to the `ReadDriversLicense` template.

The code snippet below shows the simplest implementation of *ScannerPage* that will set up and launch the Driver License Scanner. Please note that in order to use the Driver License Scanner, a **valid license must be defined in the code**.

```dart
import 'package:dynamsoft_capture_vision_flutter/dynamsoft_capture_vision_flutter.dart';
import 'package:flutter/material.dart';

import 'driver_license_scan_result.dart';

class ScannerPage extends StatefulWidget {
  const ScannerPage({super.key});

  @override
  State<ScannerPage> createState() => _ScannerPageState();
}

class _ScannerPageState extends State<ScannerPage> with RouteAware {
  final CaptureVisionRouter _cvr = CaptureVisionRouter.instance;
  final CameraEnhancer _camera = CameraEnhancer.instance;
  final String _templateName = "ReadDriversLicense";
  late final CapturedResultReceiver _receiver = CapturedResultReceiver()
    ..onParsedResultsReceived = (ParsedResult result) async {
      if (result.items?.isNotEmpty ?? false) {
        _cvr.stopCapturing();
        final data = DriverLicenseData.fromParsedResultItem(result.items![0]);
        if (data != null) {
          final scanResult = DriverLicenseScanResult(resultStatus: EnumResultStatus.finished, data: data);
          Navigator.pop(context, scanResult);
        } else {
          _cvr.startCapturing(_templateName); // restart capturing
        }
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
    await _cvr.setInput(_camera);
    _cvr.addResultReceiver(_receiver);
    _camera.open();
    try {
      await _cvr.startCapturing(_templateName);
    } catch (e) {
      Navigator.of(context).pop(
        DriverLicenseScanResult(
          resultStatus: EnumResultStatus.error,
          errorString: e.toString(),
        )
      );
    }
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
    return PopScope(
      canPop: false,
      onPopInvokedWithResult:  (bool didPop, Object? _) {
        if (didPop) {
          return;
        }
        final scanResult = DriverLicenseScanResult(resultStatus: EnumResultStatus.cancelled);
        Navigator.pop(context, scanResult);
      },
      child: Scaffold(
        appBar: AppBar(backgroundColor: Theme.of(context).colorScheme.inversePrimary, title: Text("Scanner")),
        body: Stack(
          children: [Center(child: CameraView(cameraEnhancer: _camera))],
        ),
      ),
    );
  }
}
```

> [!NOTE]
>
> - `DriverLicenseData.fromParsedResultItem()` is a helper function to convert a [`ParsedResultItem`]({{ site.dcp_flutter_api }}parsed-result-item.html) into a more user-friendly structure (`DriverLicenseData`). You can get the source code from [driver_license_scan_result.dart](https://github.com/Dynamsoft/barcode-reader-flutter-samples/blob/main/ScanDriversLicense/lib/driver_license_scan_result.dart).
>- The license string here grants a time-limited free trial which requires network connection to work.
>- You can request a 30-day trial license via the [Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=guide&package=mobile) portal.

### Implementing the DriverLicenseScanResult Class

The next step in building this app is to create the `DriverLicenseScanResult` class which will be used to represent the parsed information that is output by the library. **For the full implementation of this class, please refer to [*driver_license_scan_result.dart*]([ScanDriversLicense/lib/driver_license_scan_result.dart](https://github.com/Dynamsoft/barcode-reader-flutter-samples/blob/main/ScanDriversLicense/lib/driver_license_scan_result.dart))**. Here is a quick breakdown of the `DriverLicenseScanResult` class:

- `resultStatus` represents whether the result was produced successfully, if the scan operation was cancelled, or if an error occurred during the scanning process.
- `data` is a `DriverLicenseData` object that represents the parsed information as different string fields which can then be accessed via these key fields and presented to the user in a friendly manner.
    - `DriverLicenseData` is created from a [`ParsedResultItem`]({{ site.dcp_flutter_api }}parsed-result-item.html) object via the `fromParsedResultItem()` function that is defined in the `DriverLicenseData` class.
- `errorString` is the error message that is produced should the `resultStatus` be `exception`.

### Finalizing the App

Now that the main Scanner widget and the `DriverLicenseScanResult` class are implemented, it's time to bring them together in the *main.dart* of the project. For the full implementation of *main.dart*, please see the code below:

```dart
import 'package:flutter/material.dart';

import 'driver_license_scan_result.dart';
import 'scan_page.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  // This widget is the root of your application.
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Scan Drivers\' License',
      theme: ThemeData(colorScheme: ColorScheme.fromSeed(seedColor: Colors.orange)),
      home: const MyHomePage(title: 'Scan Drivers\' License'),
    );
  }
}

class MyHomePage extends StatefulWidget {
  const MyHomePage({super.key, required this.title});

  final String title;

  @override
  State<MyHomePage> createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  String _scanResult = '';

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(backgroundColor: Theme.of(context).colorScheme.inversePrimary, title: Text(widget.title)),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          crossAxisAlignment: CrossAxisAlignment.center,
          children: [
            Text(_scanResult, style: const TextStyle(fontSize: 16)),
            const SizedBox(height: 20),
            TextButton(
              onPressed: () async {
                final result = await Navigator.push(context, MaterialPageRoute(builder: (context) => const ScannerPage())) as DriverLicenseScanResult;

                setState(() {
                  if (result.resultStatus == EnumResultStatus.finished) {
                    _scanResult = result.data!
                        .toMap()
                        .entries
                        .map((entry) {
                          return "${entry.key}: ${entry.value}";
                        })
                        .join("\n");
                  } else if (result.resultStatus == EnumResultStatus.cancelled) {
                    _scanResult = 'Scan cancelled';
                  } else if (result.resultStatus == EnumResultStatus.error) {
                    _scanResult = 'Error message: ${result.errorString}';
                  }
                });
              },
              style: TextButton.styleFrom(backgroundColor: Colors.orange, foregroundColor: Colors.white),
              child: const Text('Open Drivers\' License Scanner'),
            ),
            const SizedBox(height: 50),
          ],
        ),
      ),
    );
  }
}
```

## Customize the Driver License Scanner

Even though the Driver License Scanner comes with a template that is optimized for the typical driver license scanning scenario, there could be situations that require a different approach in order to get handled properly. The Driver License Scanner comes with a wide range of customizations, whether it is UI related, performance related, or a mix of both.

In this next section we will explore one of the ways in which the Driver License Scanner can be customized - specifying a scan region.

### Specify the Scan Region

You can limit the scan region of the library so that it doesn't exhaust resources trying to read from the entire image or frame.

```dart
final CameraEnhancer _camera = CameraEnhancer.instance;

void initSdk() async {
  //......
  final scanRegion = DSRect(left: 0.1, top: 0.4, right: 0.9, bottom: 0.6, measuredInPercentage: true);
  _camera.setScanRegion(scanRegion);
}
```

## Run the Project

### iOS

Before the project can be deployed to a *iOS* device, the camera permissions and the developer signature must first be set. To add the camera permissions to the iOS portion of the app, we recommend first installing the **pods** dependencies to generate the **.xcworkspace** project under the ios folder (`ios/Runner.xcworkspace`). Please run the following commands from the root directory:

```bash
cd ios/
pod install --repo-update
```

#### Camera Permissions

Once the pods are installed, *Runner.xcworkspace* should now be generated in the *ios* folder. To add the camera permissions, open the generated *Runner.xcworkspace* and navigate to the *Info* section of the project settings. Then you must add the "Privacy - Camera Usage Description" key to the list (where you can also assign a string message to show in the alert box).

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

#### iOS

In order to deploy the app to a iOS device, we recommend doing it via Xcode by using the `Runner.xcworkspace` project that was generated when the pods were installed. Since the camera permissions are taken care of, all you need to do is properly configure the *Signing & Capabilities* section of the project settings. Should the iOS device be connected to the computer, you can now run and deploy the app to the device. 

If everything is set up correctly, you should see the app running on your device.

## Full Sample Code

The full sample code is available [here](https://github.com/Dynamsoft/barcode-reader-flutter-samples/tree/main/ScanDriversLicense).

## License

You can request a 30-day trial license via the [Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=github&package=mobile) portal.

## Support

https://www.dynamsoft.com/company/contact/
