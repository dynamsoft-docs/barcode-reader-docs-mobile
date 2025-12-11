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

This guide walks you through integrating a Driver License Scanner to quickly extract ID information from driver licenses.

## Supported Driver License Types

Most driver licenses include a PDF417 barcode (usually on the back) that encodes personal information. Different regions use different formats, meaning the contained fields and encoding structure can vary.

### AAMVA Driver License

The American Association of Motor Vehicle Administrators (AAMVA) defines the standard used across most North American driver licenses.
All AAMVA DL/ID specification versions (2000–2016) are supported.

### South Africa Driver License

South African driver license barcodes are partially supported. [View supported fields]({{ site.code_types }}za-dl.html).

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

## Building the Driver License Scanner Widget

The driver license workflow includes:

- Implementing the scan page
- Defining the result extraction APIs (e.g., `DriverLicenseScanResult`, `DriverLicenseData`)
- Invoking the scanner from main.dart

### Create the Scan Page

Create scan_page.dart and insert the full workflow:

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
  // Create the CaptureVisionRouter instance. The CaptureVisionRouter is the class for managing the barcode scanning process.
  final CaptureVisionRouter _cvr = CaptureVisionRouter.instance;
  // Create the camera instance 
  final CameraEnhancer _camera = CameraEnhancer.instance;
  final String _templateName = "ReadDriversLicense";
  // Define the result receiver for receiving the captured results.
  late final CapturedResultReceiver _receiver = CapturedResultReceiver()
    ..onParsedResultsReceived = (ParsedResult result) async {
      if (result.items?.isNotEmpty ?? false) {
        // Stop capturing when dealing with the results.
        _cvr.stopCapturing();
        // Transfer the parsed result into driver license format data.
        final data = DriverLicenseData.fromParsedResultItem(result.items![0]);
        if (data != null) {
          final scanResult = DriverLicenseScanResult(resultStatus: EnumResultStatus.finished, data: data);
          Navigator.pop(context, scanResult);
        } else {
          // If data == null, restart capturing
          _cvr.startCapturing(_templateName);
        }
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
    // Stop capturing, close the camera, and remove the result receiver when disposing.
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
>- The license string here grants a time-limited free trial which requires network connection to work.
>- You can request a 30-day trial license via the [Request a Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=guide&package=flutter){:target="_blank"} link.

Related APIs:

- [`LicenseManager`]({{ site.dcv_flutter_api }}license/license-manager.html) - licensing.
- [`CameraEnhancer`]({{ site.dce_flutter_api }}camera-enhancer.html) - camera operations
- [`CaptureVisionRouter`]({{ site.dcv_flutter_api }}capture-vision-router/capture-vision-router.html) - manages the scanning workflow
- [`CapturedResultReceiver`]({{ site.dcv_flutter_api }}capture-vision-router/captured-result-receiver.html) - receives processed results

### Define Result Models

Create `driver_license_scan_result.dart` and include the data structures used to represent parsed driver license fields.

```dart
import 'package:dynamsoft_capture_vision_flutter/dynamsoft_capture_vision_flutter.dart';

enum EnumResultStatus {
  finished,
  cancelled,
  error,
}

class DriverLicenseScanResult {
  // Represents whether the result was produced successfully, if the scan operation was cancelled, or if an error occurred during the scanning process.
  EnumResultStatus resultStatus;
  // When the resultStatus is "exception". You will receive the error message here. 
  String? errorString = "";
  // A DriverLicenseData object that represents the parsed information as different string fields. Created from a ParsedResultItem.
  DriverLicenseData? data;
  DriverLicenseScanResult({
    required this.resultStatus,
    this.errorString,
    this.data,
  });
}

class DriverLicenseData {
  String documentType;
  String? name;
  String? state; //For AAMVA_DL_ID
  String? stateOrProvince; //For AAMVA_DL_ID_WITH_MAG_STRIPE
  String? initials; //For SOUTH_AFRICA_DL
  String? city; //For AAMVA_DL_ID, AAMVA_DL_ID_WITH_MAG_STRIPE
  String? address; //For AAMVA_DL_ID, AAMVA_DL_ID_WITH_MAG_STRIPE
  String? idNumber; //For SOUTH_AFRICA_DL
  String? idNumberType; //For SOUTH_AFRICA_DL
  String? licenseNumber;
  String? licenseIssueNumber; //For SOUTH_AFRICA_DL
  String? issuedDate;
  String? expirationDate;
  String? birthDate;
  String? sex;
  String? height; //For AAMVA_DL_ID, SOUTH_AFRICA_DL
  String? issuedCountry; //For AAMVA_DL_ID, SOUTH_AFRICA_DL
  String? vehicleClass;  //For AAMVA_DL_ID
  String? driverRestrictionCodes; //For SOUTH_AFRICA_DL
  DriverLicenseData({
    required this.documentType
  });

  Map<String, String> toMap() {
    return {
      'documentType': documentType,
      if (name != null) 'name': name!,
      if (state != null) 'state': state!,
      if (stateOrProvince != null) 'stateOrProvince': stateOrProvince!,
      if (initials != null) 'initials': initials!,
      if (city != null) 'city': city!,
      if (address != null) 'address': address!,
      if (idNumber != null) 'idNumber': idNumber!,
      if (idNumberType != null) 'idNumberType': idNumberType!,
      if (licenseNumber != null) 'licenseNumber': licenseNumber!,
      if (licenseIssueNumber != null) 'licenseIssueNumber': licenseIssueNumber!,
      if (issuedDate != null) 'issuedDate': issuedDate!,
      if (expirationDate != null) 'expirationDate': expirationDate!,
      if (birthDate != null) 'birthDate': birthDate!,
      if (sex != null) 'sex': sex!,
      if (height != null) 'height': height!,
      if (issuedCountry != null) 'issuedCountry': issuedCountry!,
      if (vehicleClass != null) 'vehicleClass': vehicleClass!,
      if (driverRestrictionCodes != null) 'driverRestrictionCodes': driverRestrictionCodes!,
    };
  }

  static DriverLicenseData? fromParsedResultItem(ParsedResultItem item) {
    var codeType = item.codeType;
    var parsedFields = item.parsedFields;
    if(parsedFields.isEmpty) {
      return null;
    }
    var data = DriverLicenseData(documentType: codeType);
    if(codeType == 'AAMVA_DL_ID') {
      data.name = parsedFields['fullName']?.value ??
          "${parsedFields['givenName']?.value ?? parsedFields['givenName']?.value ??""} ${parsedFields['lastName']?.value ?? ''}";
      data.city = parsedFields['city']?.value;
      data.state = parsedFields['jurisdictionCode']?.value;
      data.address = "${parsedFields['street_1']?.value??""} ${parsedFields['street_2']?.value??""}";
      data.licenseNumber = parsedFields['licenseNumber']?.value;
      data.issuedDate = parsedFields['issuedDate']?.value;
      data.expirationDate = parsedFields['expirationDate']?.value;
      data.birthDate = parsedFields['birthDate']?.value;
      data.height = parsedFields['height']?.value;
      data.sex = parsedFields['sex']?.value;
      data.issuedCountry = parsedFields['issuedCountry']?.value;
      data.vehicleClass = parsedFields['vehicleClass']?.value;
    } else if(codeType == 'AAMVA_DL_ID_WITH_MAG_STRIPE') {
      data.name = parsedFields['name']?.value;
      data.city = parsedFields['city']?.value;
      data.stateOrProvince = parsedFields['stateOrProvince']?.value;
      data.address = parsedFields['address']?.value;
      data.licenseNumber = parsedFields['DLorID_Number']?.value;
      data.expirationDate = parsedFields['expirationDate']?.value;
      data.birthDate = parsedFields['birthDate']?.value;
      data.height = parsedFields['height']?.value;
      data.sex = parsedFields['sex']?.value;
    } else if(codeType == 'SOUTH_AFRICA_DL') {
      data.name = parsedFields['surname']?.value;
      data.idNumber = parsedFields['idNumber']?.value;
      data.idNumberType = parsedFields['idNumberType']?.value;
      data.licenseNumber = parsedFields['idNumber']?.value ?? parsedFields['licenseNumber']?.value;
      data.licenseIssueNumber = parsedFields['licenseIssueNumber']?.value;
      data.initials = parsedFields['initials']?.value;
      data.issuedDate = parsedFields['licenseValidityFrom']?.value;
      data.expirationDate = parsedFields['licenseValidityTo']?.value;
      data.birthDate = parsedFields['birthDate']?.value;
      data.sex = parsedFields['gender']?.value;
      data.issuedCountry = parsedFields['idIssuedCountry']?.value;
      data.driverRestrictionCodes = parsedFields['driverRestrictionCodes']?.value;
    }
    return data;
  }
}
```

### Navigating to Scan Page

Add navigation logic in `main.dart` to trigger the scanner and display results.

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

### Customize the Driver License Scanner (Optional)

Although the Driver License Scanner template is optimized for common scenarios, you may customize performance or UI behavior as needed.

#### Specify the Scan Region

Restricting the scan region can reduce processing time and avoid reading unwanted areas:

```dart
void initSdk() async {
  final scanRegion = DSRect(left: 0.1, top: 0.4, right: 0.9, bottom: 0.6, measuredInPercentage: true);
  _camera.setScanRegion(scanRegion);
}
```

## Run the Project

### iOS

1. Install CocoaPods dependencies

   Before the project can be deployed to a *iOS* device, the camera permissions and the developer signature must first be set. To add the camera permissions to the iOS portion of the app, we recommend first installing the **pods** dependencies to generate the **.xcworkspace** project under the ios folder (`ios/Runner.xcworkspace`). Please run the following commands from the root directory:

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

The full sample code is available [here](https://github.com/Dynamsoft/barcode-reader-flutter-samples/tree/main/ScanDriversLicense).

## License

You can request a 30-day trial license via the [Request a Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=guide&package=mobile){:target="_blank"} link.

## Support

[https://www.dynamsoft.com/company/contact/](https://www.dynamsoft.com/company/contact/)
