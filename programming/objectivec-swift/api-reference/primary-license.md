---
layout: default-layout
title: License Methods - Dynamsoft Barcode Reader iOS API Reference
description: This page shows License methods of Dynamsoft Barcode Reader for iOS SDK.
keywords: initWithLicense, initWithLicenseFromServer, outputLicenseToString, license methods, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
noTitleIndex: true
multiProgrammingLanguage: true
enableLanguageSelection: true
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

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
+ (void)initLicense:(nonnull NSString *)license verificationDelegate:(nonnull id<DBRLicenseVerificationListener>)listener 
NS_SWIFT_NAME(initLicense(_:verificationDelegate:));
```
2. 
```swift
class func initLicense(_ license: String, verificationDelegate listener: DBRLicenseVerificationListener)
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

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
+ (BOOL)setDeviceFriendlyName:(NSString *_Nullable)name error:(NSError *_Nullable *_Nullable)error;
```
2. 
```swift
class func setDeviceFriendlyName(_ name: String?) throws
```

**Parameters**

`[in] name` The user-defined device name.  
`[in,out] error`: A pointer to an error object.

An error occurs when:

- Failed to set device friendly name.

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
do{
   try DynamsoftBarcodeReader.setDeviceFriendlyName("Put your device name here")
}catch{
   // Add your code to deal with exceptions
}
```
