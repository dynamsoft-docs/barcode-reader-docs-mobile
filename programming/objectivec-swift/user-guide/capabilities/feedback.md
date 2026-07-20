---
layout: default-layout
title: Add Scan Feedback for BarcodeScanner - Dynamsoft Barcode Reader iOS
description: Learn how to enable scan feedback for BarcodeScanner on iOS, including beep and vibration.
keywords: BarcodeScanner, scanner, iOS, feedback, beep, vibration
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Add Scan Feedback

Trigger a beep sound or vibration when a barcode is scanned successfully.

### Use Foundational APIs

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[DSFeedback beep];
[DSFeedback vibrate];
```
2. 
```swift
Feedback.beep()
Feedback.vibrate()
```

**Related API**

- [`Feedback`]({{ site.dce_ios }}auxiliary-api/dcefeedback.html)

### Use BarcodeScanner APIs

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DSBarcodeScannerConfig *config = [[DSBarcodeScannerConfig alloc] init];
config.isBeepEnabled = YES;
config.isVibrateEnabled = YES;
```
2. 
```swift
let config = BarcodeScannerConfig()
config.isVibrateEnabled = true
config.isBeepEnabled = true
```

**Related API**

- [`isVibrateEnabled`]({{ site.dbr_ios_api }}barcode-scanner/barcode-scanner-config.html#isvibrateenabled)
- [`isBeepEnabled`]({{ site.dbr_ios_api }}barcode-scanner/barcode-scanner-config.html#isbeepenabled)
