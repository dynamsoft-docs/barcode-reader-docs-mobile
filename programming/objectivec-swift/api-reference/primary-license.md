---
layout: default-layout
title: Dynamsoft Barcode Reader Objective-C & Swift API Reference - License Methods
description: This page shows License methods of Dynamsoft Barcode Reader for iOS SDK.
keywords: initWithLicense, initWithLicenseFromServer, outputLicenseToString, license methods, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
noTitleIndex: true
permalink: /programming/objectivec-swift/api-reference/primary-license.html
---

# License Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`initLicense`](#initlicense) | Initialize license for `DynamsoftBarcodeReader`. |
  | [`setDeviceFriendlyName`](#setdevicefriendlyname) | Sets a human-readable name that identifies the device. |
  
  ---

## initLicense

Initializes `DynamsoftBarcodeReader` with a license.

```objc
+ (void)initLicense:(nonnull NSString *)license verificationDelegate:(nonnull id<DBRLicenseVerificationListener>)listener 
NS_SWIFT_NAME(initLicense(_:verificationDelegate:));
```

**Parameters**

`[in] license` The license key.
`[in, out] verificationDelegate` The listener that handles callback when the license verification message is returned by the license server. See also [`DBRLicenseVerificationListener`](protocol-dbrlicenseverificationlistener.md).

**Return Value**

The instance of `DynamsoftBarcodeReader`.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[DynamsoftBarcodeReader initLicense:@"Put your license here" verificationDelegate: self];
- (void)DBRLicenseVerificationCallback:(bool)isSuccess error:(NSError *)error{
}
```
2. 
```swift
DynamsoftBarcodeReader.initLicense("Put your license here", verificationDelegate: self)
func dbrLicenseVerificationCallback(_ isSuccess: Bool, error: Error?) {
}
```

## setDeviceFriendlyName

Sets a human-readable name that identifies the device. This name will appear in the device details table when you check the statistics of the according license.

```objc
+ (BOOL)setDeviceFriendlyName:(NSString *_Nullable)name error:(NSError *_Nullable *_Nullable)error;
```

**Parameters**

`[in] name` The user-defined device name.  
`[in, out] error` Input a pointer to an error object. If an error occurs, this pointer is set to an actual error object containing the error information. You may specify nil for this parameter if you do not want the error information.  

**Return Value**

A BOOL value that indicates whether the device name setting is approved.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[DynamsoftBarcodeReader setDeviceFriendlyName:@"Put your device name here" error:&error];
```
2. 
```swift
try? DynamsoftBarcodeReader.setDeviceFriendlyName("Put your device name here")
```
