---
layout: default-layout
title: Dynamsoft Barcode Reader for iOS - General Settings Sample
description: This is the General Settings Sample page of Dynamsoft Barcode Reader for iOS SDK.
keywords: iOS, samples, General
needAutoGenerateSidebar: true
breadcrumbText: GeneralSettings
permalink: /programming/objectivec-swift/samples/general.html
---

# GeneralSettings Sample

This sample shows general barcode decoding settings and how to configure the settings when using Dynamsoft Barcode Reader iOS SDK. You can see the following settings in the sample:

- [Scan Mode]()
- [Barcode Format & Expected Barcode Count](#barcode-formats--expected-barcode-count)
- [Inverted Barcode Decoding]
- [Minimum Decode Interval]()
- [Duplicate Filter]()
- [Minimum Result Confidence]()
- [Result Verification]()
- Scan Region
- Display of Overlay
- Vibration & Beep
- Torch Control

**View the Sample(s)**

- <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/Objective-C/GeneralSettingsObjC/" target="_blank">Objective-C General Settings Sample</a>
- <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/Swift/GeneralSettingsSwift/" target="_blank">Swift General Settings Sample</a>

## Scan Mode

- Continuous Scan: Decode the barcodes from the video streaming continuously. You can add
- One-off Scan: Stop scanning when a barcode is decoded from the video streaming.

The video barcode decoding of Dynamsoft Barcode Reader is designed to be continuous, which means once you triggered method `startScanning`, the video barcode decoding will not stop until you call method `stopScanning`. The **One-off Scan** mode of **GeneralSettings sample** is configured by triggering `stopScanning` when the barcode results are returned by `textResultCallback`.

## Barcode Formats & Expected Barcode Count

The barcode formats settings and the barcode count settings are the most basic settings that determine the readability of your scan app. These parameters are all available for users to make changes through the class [`PublicRuntimeSettings`]({{ site.oc_api }}auxiliary-iPublicRuntimeSettings.html). To view all available barcode formats, please view the enumeration [`BarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=objc,swift) and [`BarcodeFormat_2`]({{ site.mobile_enum }}barcode-format2.html?lang=objc,swift).

## Inverted Barcode Decoding

If you are working with inverted barcodes, `GrayscaleTransformationModes` is the parameter to deal with them.

<div align="center">
    <p><img src="../../assets/inverted-barcode.png" width="20%" alt="invert"></p>
    <p>Inverted Barcode</p>
</div>

The candidate modes are:

- `GTM_ORIGINAL`: Decode original coloured barcode.
- `GTM_INVERTED`: Decode inverted barcode.

There are 2 ways for you to configure the algorithm parameters. You can either upload the PublicRuntimeSettings 

### Update the Settings

### Via JSON Template

Besides using the [`PublicRuntimeSettings`]({{ site.oc_api }}auxiliary-iPublicRuntimeSettings.html) class, you can also upload the general barcode settings from stringified JSON data or a JSON file.

#### From JSON String

Use method [`initRuntimeSettingsWithString`]({{ site.oc_api }}primary-parameter-and-runtime-settings-advanced.html#initruntimesettingswithstring) to upload the settings via a JSON string.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSString* json = @"{\"Version\":\"3.0\", \"ImageParameter\":{\"Name\":\"IP1\", \"BarcodeFormatIds\":[\"BF_QR_CODE\"], \"ExpectedBarcodesCount\":10}}";
[_barcodeReader initRuntimeSettingsWithString:json conflictMode:EnumConflictModeOverwrite error:nil];
```
2. 
```swift
let json = "{\"Version\":\"3.0\", \"ImageParameter\":{\"Name\":\"IP1\", \"BarcodeFormatIds\":[\"BF_QR_CODE\"], \"ExpectedBarcodesCount\":10}}"
try? barcodeReader.initRuntimeSettingsWithString(json, conflictMode: .overwrite)
```

#### From JSON File

Use method [`initRuntimeSettingsWithFile`]({{ site.oc_api }}primary-parameter-and-runtime-settings-advanced.html#initruntimesettingswithfile) to upload the settings via a JSON file.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
// The method will overwrite the settings if the settings already exist.
[barcodeReader initRuntimeSettingsWithFile:@"your template file path" conflictMode:EnumConflictModeOverwrite error:nil];
```
2. 
```swift
// The method will overwrite the settings if the settings already exist.
try? barcodeReader.initRuntimeSettingsWithFile("your template file path", conflictMode:EnumConflictMode.overwrite)
```

**Related APIs**

- Class [`PublicRuntimeSettings`]({{ site.oc_api }}auxiliary-iPublicRuntimeSettings.html)
- Enum [`BarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=objc,swift)
- Enum [`BarcodeFormat_2`]({{ site.mobile_enum }}barcode-format2.html?lang=objc,swift)

## Minimum Decode Interval

## Duplicate Filter

## Minimum Result Confidence

## Result Verification

## Scan Region

For video barcode decoding scenarios, specifying a **scanRegion** can reduce the size of the processing area, which sharply increases the barcode decoding speed. To specify the scan region, you can use the **CameraEnhancer** method <a href="https://www.dynamsoft.com/camera-enhancer/docs/programming/ios/primary-api/camera-enhancer.html?ver=latest#setscanregion" target="_blank">`setScanRegion`</a>. When the **scanRegion** is configured via **CameraEnhancer**, the video frames will be cropped based on the **scanRegion** before being processed by the barcode reader.

## Display of Overlay

## Vibration & Beep

## Torch Control
