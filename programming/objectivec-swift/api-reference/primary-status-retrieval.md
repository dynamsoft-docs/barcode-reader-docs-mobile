---
layout: default-layout
title: BarcodeReader Status Retrieval Methods - Dynamsoft Barcode Reader iOS API Reference
description: This page shows BarcodeReader status retrieval methods of Dynamsoft Barcode Reader for iOS SDK.
keywords: getVersion, status retrieval methods, BarcodeReader, api reference, iOS
needAutoGenerateSidebar: true
noTitleIndex: true
permalink: /programming/objectivec-swift/api-reference/primary-status-retrieval.html
---

# Status Retrieval Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`getVersion`](#getversion) | Get version information of SDK.|
  | [`setLogConfig`](#setlogconfig) | Set the directory and the saving mode of log. It helps you on debugging. |

  ---

## getVersion

Get version information of SDK.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
+ (NSString *_Nullable)getVersion;
```
2. 
```swift
class func getVersion() -> String?
```

**Return Value**

The version of `DynamsoftBarcodeReader` iOS SDK and `DynamsoftBarcodeReader` algorithm.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSString *version = [DynamsoftBarcodeReader getVersion];
```
2. 
```swift
let version = DynamsoftBarcodeReader.getVersion();
```

## setLogConfig

Set the directory and the saving mode of log. It helps you on debugging.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (BOOL)setLogConfig:(NSString*)logDir
                mode:(EnumLogMode)mode
               error:(NSError* _Nullable * _Nullable)error;
```
2. 
```swift
func setLogConfig(_ logDir: String, mode: Int) throws
```

**Parameters**

`[in] logDir`: Where to save the log.
`[in] mode`: The saving mode of the log.
`[in,out] error`: A pointer to an error object.

An error occurs when:

- The directory you input is invalid.

**Return Value**

A boolean value that indicates whether the log config is approved.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[DynamsoftBarcodeReader setLogConfig:"" mode:EnumLogMode.LM_TEXT error:nil];
```
2. 
```swift
do{
   try DynamsoftBarcodeReader.setLogConfig("", mode:EnumLogMode.LM_TEXT, error:nil);
}catch{
   // Add your code to deal with exceptions
}
```
