---
layout: default-layout
title: LicenseManager Class - Dynamsoft Capture Vision Flutter
description: LicenseManager class of DCV Flutter provides API to initialize and verify product licenses.
keywords: license, manager, barcode reader, flutter, capture vision
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# LicenseManager

The `LicenseManager` class provides the API needed to initialize and verify the licenses for the functional products that are being used by the `CaptureVisionRouter` instance. For example, if the `CaptureVisionRouter` instance is using the Barcode Reader, then the `LicenseManager` must include a valid Barcode Reader license. If it is using both the Barcode Reader and the Code Parser, then the `LicenseManager` must include a license for each product.

## Definition

*Assembly:* dynamsoft_capture_vision_flutter

```dart
class LicenseManager
```

## Methods

### initLicense

Initializes the license for the application using the provided license key. A single **license key** can contain a license for a single product or licenses for multiple products - depending on the functional product(s) that the CaptureVisionRouter will utilize.

```dart
Future<(bool, String?)> initLicense( String license )
```

**Code Snippet**

```dart
final result = await LicenseManager.initLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9");
if (result.isSuccess) {
  print("License initialized successfully");
} else {
  print("License initialization failed: ${result.message}");
}
```