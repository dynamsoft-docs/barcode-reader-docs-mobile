---
layout: default-layout
title: Initialize Customized Templates - Dynamsoft Barcode Reader iOS User Guide
description: Learn how to initialize customized templates in the Dynamsoft Barcode Reader iOS SDK.
keywords: customized templates, iOS, objective-c, swift
noTitleIndex: true
needGenerateH3Content: true
needAutoGenerateSidebar: true
---

# How to Initialize Customized Templates

Using a template file is one of the quickest ways to improve BarcodeScanner performance. A template file is a JSON file (or JSON string) that contains a set of algorithm parameter settings. [Contact us](https://www.dynamsoft.com/company/customer-service/#contact) to get a customized template for your scanner.

## Preparation

Add a **Templates** folder under your project's assets directory at **src\main\assets\Templates**. Put your JSON file in the **Templates** folder. Here, we use **ReadQRCode.json** as an example.

<div align="left">
<p><img src="../../../assets/init-settings-from-file-iOS.png" alt="initSettings" width="50%" /></p>
</div>

## Initialize with Foundational APIs

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSError *error = nil;
[self.cvr initSettingsFromFile:@"ReadQRCodes.json" error:&error];
```
2. 
```swift
try cvr.initSettingsFromFile("ReadQRCodes.json")
```

## Initialize with BarcodeScanner APIs

Specify the template file with `setTemplateFile`.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DSBarcodeScannerConfig *config = [[DSBarcodeScannerConfig alloc] init];
config.templateFile = @"ReadQRCodes.json";
```
2. 
```swift
let config = BarcodeScannerConfig()
config.templateFile = "ReadQRCodes.json"
```

**Related APIs**

- [`setTemplateFile`]({{ site.dbr_ios_api }}barcode-scanner/barcode-scanner-config.html#settemplatefile)
