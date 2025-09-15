---
layout: default-layout
title: Getting Started with Barcode Reader - Dynamsoft Capture Vision Flutter Edition
description: This is the user guide of Dynamsoft Capture Vision Flutter edition - Barcode Reader module
keywords: User guide, Barcode Reader, Flutter, Capture Vision, Dynamsoft
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: Guide of Dynamsoft Barcode Reader Flutter
---

# Barcode Reader User Guide for Flutter

In this guide, we will explore the Barcode Reader module of the Dynamsoft Capture Vision library for Flutter.

## Table of Contents

- [System Requirements](#system-requirements)
- [Installation](#installation)
- [Build Your Barcode Scanner App](#build-your-barcode-scanner-app)
  - [Set up Development Environment](#set-up-development-environment)
  - [Initialize the Project](#initialize-the-project)
  - [Include the Library](#include-the-library)
  - [License Activation](#license-activation)
  - [Configure the Barcode Reader](#configure-the-barcode-reader)
  - [Build the Widget](#build-the-widget)
  - [Run the Project](#run-the-project)
- [Customizing the Barcode Reader](#customizing-the-barcode-reader)
  - [Using the Settings Templates](#using-the-settings-templates)
  - [Using the DBRRuntimeSettings Interface](#using-the-dbrruntimesettings-interface)
  - [Customizing the Scan Region](#customizing-the-scan-region)
- [Licensing](#licensing)

## System Requirements

### Flutter & Dart

- Flutter version: >=2.0.0
- Dart version: >=2.12.0 <3.0.0

### Android

- Supported OS: Android 5.0 (API Level 21) or higher.
- Supported ABI: **armeabi-v7a**, **arm64-v8a**, **x86** and **x86_64**.
- Development Environment: Android Studio 3.4+ (Android Studio 4.2+ recommended).
- JDK: 1.8+

### iOS

- Supported OS: **iOS 10.0** or higher.
- Supported ABI: **arm64** and **x86_64**.
- Development Environment: Xcode 7.1 and above (Xcode 13.0+ recommended), CocoaPods 1.11.0+.

## Installation

Run the following command:

```bash
flutter pub add dynamsoft_capture_vision_flutter
```

This will add a line like this to your package's `pubspec.yaml` (and run an implicit flutter pub get):

```dart
dependencies:
   dynamsoft_capture_vision_flutter: ^1.2.0
```

## Build Your Barcode Scanner App

Now you will learn how to create a simple barcode scanner using Dynamsoft Capture Vision Flutter SDK.

>Note: You can get the full source code of a similar project:  [Barcode Reader Simple Sample](https://github.com/Dynamsoft/capture-vision-flutter-samples/tree/main/barcode_reader_simple_sample)

### Set up Development Environment

If you are a beginner with Flutter, please follow the guide on the <a href="https://docs.flutter.dev/get-started/install" target="_blank">Flutter official website</a> to set up the development environment.

### Initialize the Project

Create a new Flutter project.

```bash
flutter create simple_barcode_scanner
```

### Include the Library

View the [installation section](#installation) on how to add the library. In **main.dart** of your project, import the library.

```dart
import 'package:dynamsoft_capture_vision_flutter/dynamsoft_capture_vision_flutter.dart';
```

### License Activation

The barcode reading module of Dynamsoft Capture Vision needs a valid license to work. Please refer to the [Licensing](#licensing) section for more info on how to obtain a license. In the `main()` function, add the following code to activate the license:

```dart
void main() async {
  WidgetsFlutterBinding.ensureInitialized();
  // Put your Dynamsoft Barcode Reader license here.
  const String licenseKey = '';
  // Initialize the license so that you can use full feature of the Barcode Reader module.
  try {
    await DCVBarcodeReader.initLicense(licenseKey);
  } catch (e) {
    print(e);
  }

  runApp(const MyApp());
}
```

### Configure the Barcode Reader

In this section, we are going to work on the `_MyHomePageState` class in the newly created project to add the barcode decoding feature.

Add the following instance variables:

```dart
class _MyHomePageState extends State<MyHomePage> with WidgetsBindingObserver{
  late final DCVBarcodeReader _barcodeReader;
  late final DCVCameraEnhancer _cameraEnhancer;
  final DCVCameraView _cameraView = DCVCameraView();
  List<BarcodeResult> decodeResults = [];
}
```

- `_barcodeReader`: The object that implements the barcode decoding feature. Users can configure barcode decoding settings via this object.
- `_cameraView`: The camera view that displays the video stream (from a camera input).
- `_cameraEnhancer`: The object that enables you to control the camera.
- `decodeResults`: An object that will be used to receive and store barcode decoding results.

Add **_configDBR** method to initialize the barcode reader:

```dart
class _MyHomePageState extends State<MyHomePage> with WidgetsBindingObserver{
  ...
  @override
  void initState() {
    super.initState();
    WidgetsBinding.instance.addObserver(this);
    _configDBR();
  }

  @override
  void dispose() {
    WidgetsBinding.instance.removeObserver(this);
    _cameraEnhancer.close();
    _barcodeReader.stopScanning();
    super.dispose();
  }

  @override
  void didChangeAppLifecycleState(AppLifecycleState state) {
    super.didChangeAppLifecycleState(state);

    switch (state) {
      case AppLifecycleState.resumed:
        _barcodeReader.startScanning();
        _cameraEnhancer.open();
        break;
      case AppLifecycleState.inactive:
        _cameraEnhancer.close();
        _barcodeReader.stopScanning();
        break;
    }
  }

  _configDBR() async {
    /// Create an instance of barcode reader.
    _barcodeReader = await DCVBarcodeReader.createInstance();
    /// Create an instance of camera enhancer.
    _cameraEnhancer = await DCVCameraEnhancer.createInstance();

    /// When overlayVisible is set to true, the decoded barcodes will be highlighted with overlays.
    _cameraView.overlayVisible = true;

    /// Receive the barcode decoding results and store the result in object decodeResults
    _barcodeReader.receiveResultStream().listen((List<BarcodeResult> res) {
      if (mounted) {
        setState(() {
          decodeRes = res ?? [];
        });
      }
    });

    await _cameraEnhancer.open();

    /// Start barcode decoding when the widget is created.
    _barcodeReader.startScanning();
  }
}
```

Add configurations to parse and display the barcode decoding results:

```dart
class _MyHomePageState extends State<MyHomePage> with WidgetsBindingObserver{
  ...
  /// Get listItem
  Widget listItem(BuildContext context, int index) {
    BarcodeResult res = decodeResults[index];

    return ListTileTheme(
        textColor: Colors.white,
        child: ListTile(
          title: Text(res.barcodeFormatString),
          subtitle: Text(res.barcodeText),
        ));
  }
}
```

### Build the Widget

Modify the `build` method to display the decode barcode results on the widget.

```dart
class _MyHomePageState extends State<MyHomePage> with WidgetsBindingObserver{
  ...
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('HelloWorld'),
      ),
      body: Stack(
        children: [
          Container(
            child: _cameraView,
          ),
          Container(
            height: 100,
            child: ListView.builder(
              itemBuilder: listItem,
              itemCount: decodeResults.length,
            ),
          ),
          Positioned(
            top: 150,
            left: 25,
            child: GestureDetector(
              onTap: () {
                faceLens = !faceLens;
                _cameraEnhancer.selectCamera(faceLens
                    ? EnumCameraPosition.CP_FRONT
                    : EnumCameraPosition.CP_BACK);
              },
              child: Image.asset(
                'assets/toggle_lens.png',
                width: 48,
                height: 48,
              ),
            ),
          ),
        ],
      ));
  }
}
```

### Run the Project

#### Run Android on Windows

Go to the file **build.gradle(app)**, update the `minSdkVersion` to 21.

```gradle
android {
   defaultConfig {
      ...
      minSdkVersion 21
      ...
   }
}
```

In the root of your project run the following command to build and install the app:

```bash
flutter run
```

#### Run iOS on macOS

In the project folder, go to file ios/Runner/info.plist, add the following code for requesting camera permission:

```xml
<plist version="1.0">
<dict>
  ...
  <key>NSCameraUsageDescription</key>
  <string>Request your authorization.</string>
  ...
</dict>
```

Go to the **Podfile** in **ios** folder and add the following code at the top of the file:

```objc
platform:ios, '10.0'
```

In the root of your project run the following command to build and install the app:

```bash
flutter run
```

>Note: You can get the full source code of a similar project:  [Barcode Reader Simple Sample](https://github.com/Dynamsoft/capture-vision-flutter-samples/tree/main/barcode_reader_simple_sample)

## Customizing the Barcode Reader

### Using the Settings Templates

DBR offers several preset templates for different popular scenarios. For example, to prioritize speed over accuracy, you can use one of the speed templates and choose the corresponding template for images or video, and vice versa if you're looking to prioritize read rate and accuracy over speed. For the full set of templates, please refer to `EnumPresetTemplate`. Here is a quick example:

```dart
await _barcodeReader.updateRuntimeSettingsFromTemplate(EnumDBRPresetTemplate.VIDEO_READ_RATE_FIRST );
```

### Using the DBRRuntimeSettings Interface

The SDK also supports a more granular control over the individual runtime settings rather than using a preset template. The main settings that you can control via this interface are which barcode formats to read, the expected number of barcodes to be read in a single image or frame, and the timeout. For more info on each, please refer to `DBRRuntimeSettings`. Here is a quick example:

```dart
DBRRuntimeSettings currentSettings = await _barcodeReader.getRuntimeSettings();
currentSettings.barcodeFormatIds = EnumBarcodeFormat.BF_ONED;
currentSettings.expectedBarcodeCount = 10;
currentSettings.timeout = 500;
try {
   await _barcodeReader.updateRuntimeSettings(currentSettings);
} catch (e) {
   print('error = $e');
}
```

### Customizing the Scan Region

You can also limit the scan region of the SDK so that it doesn't exhaust resources trying to read from the entire image or frame. In order to do this, we will need to use the `Region` class as well as the `DCVCameraEnhancer` class.

First, let's create an instance of `DCVCameraEnhancer`. Next, we will create a scan region using the `Region` class. In this example, we define a rectangular `Region` whose dimensions are measured as a percentage of the total dimensions. Finally call the `setScanRegion` method to apply the scan region:

```dart
final DCVCameraEnhancer _cameraEnhancer = await DCVCameraEnhancer.createInstance();
Region scanRegion = Region(regionTop: 20, regionBottom: 80, regionLeft: 20, regionRight: 80, regionMeasuredByPercentage: true);
_cameraEnhancer.setScanRegion(scanRegion);
```

### Others

View the API reference to see how to use other features of Dynamsoft Capture Vision:

- [Switch to front-facing camera](../api-reference/camera-enhancer.md#selectcamera)
- Torch control
  - [Turn on/off torch](../api-reference/camera-enhancer.md#turnontorch)
  - [Add a torch button](../api-reference/camera-view.md#torchbutton)

## Licensing

- The `BarcodeReader` module of Dynamsoft Capture Vision needs a valid license to work.
- A one-day trial license is available by default for every new device to try Dynamsoft Capture Vision.
>- You can request a 30-day trial license via the [Request a Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=guide&package=flutter&version=9){:target="_blank"} link.
- [Contact us](https://www.dynamsoft.com/company/contact/) to purchase a full license.
