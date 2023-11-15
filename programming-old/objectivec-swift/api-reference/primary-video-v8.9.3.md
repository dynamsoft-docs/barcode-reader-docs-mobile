---
layout: default-layout
title: Video Methods - Dynamsoft Barcode Reader iOS API Reference
description: This page shows Video methods of Dynamsoft Barcode Reader for iOS SDK.
keywords: video barcode decoding, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
noTitleIndex: true
multiProgrammingLanguage: true
enableLanguageSelection: true
permalink: /programming/objectivec-swift/api-reference/primary-video-v8.9.3.html
---

# Video Decoding Methods

| Method               | Description |
|----------------------|-------------|
| [`setCameraEnhancer`](#setcameraenhancer) | Bind a Camera Enhancer instance to the Barcode Reader.  |
| [`startScanning`](#startscanning) | Start the barcode reading thread. |
| [`stopScanning`](#stopscanning) | Stop the barcode reading thread. |
| [`setDBRTextResultDelegate`](#setdbrtextresultdelegate) | Set callback function to process text results generated during frame decoding. |
| [`setDBRIntermediateResultDelegate`](#setdbrintermediateresultdelegate) | Set callback function to process intermediate results generated during frame decoding. |
| [`enableResultVerification`](#enableresultverification) | Enable **Result Verification** feature to improve the accuracy of barcode results for video streaming barcode decoding. |
| [`enableDuplicateFilter`](#enableduplicatefilter) | Enable **Duplicate Filter** feature to filter out the duplicate results in the period of 3000ms for video barcode decoding. |

---

## setCameraEnhancer

Bind a `Dynamsoft Camera Enhancer` instance to the Barcode Reader. `Dynamsoft Camera Enhancer` is designed for video streaming processing scenarios. It can help the Barcode Reader to acquire video frames continuously for video streaming barcode decoding.

```objc
- (void)setCameraEnhancer:(DynamsoftCameraEnhancer* _Nonnull)cameraInstance;
```

**Parameters**

`dce`: An instance of `Dynamsoft Camera Enhancer`.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, strong) DynamsoftBarcodeReader *barcodeReader;
@property(nonatomic, strong) DynamsoftCameraEnhancer *dce;
[_barcodeReader setCameraEnhancer:_dce];
```
2. 
```swift
var dce:DynamsoftCameraEnhancer! = nil
var barcodeReader:DynamsoftBarcodeReader! = nil
barcodeReader.setCameraEnhancer(dce)
```

## startScanning

Start the video streaming barcode decoding thread. Please be sure that you have bound a Camera Enhancer to the barcode reader before you trigger `startScanning`.

```objc
-(void)startScanning;
```

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[_barcodeReader startScanning];
```
2. 
```swift
barcodeReader.startScanning()
```

## stopScanning

Stop the video streaming barcode decoding thread.

```objc
-(void)stopScanning;
```

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[_barcodeReader stopScanning];
```
2. 
```swift
barcodeReader.stopScanning()
```

## setDBRTextResultDelegate

Set callback function to process text results generated during frame decoding.

```objc
-(void)setDBRTextResultDelegate:(id _Nullable)textResultDelegate userData:(NSObject* _Nullable)userData;
```

**Parameters**

`[in] textResultDelegate`: Callback function.  
`[in] userData`: Customized arguments passed to your function.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[barcodeReader setDBRTextResultDelegate:self userData:nil];
```
2. 
```swift
barcodeReader.setDBRTextResultDelegate(self, userData:nil)
```

## setDBRIntermediateResultDelegate

Set callback function to process intermediate results generated during frame decoding.

```objc
-(void)setDBRIntermediateResultDelegate:(id _Nullable)intermediateResultDelegate userData:(NSObject* _Nullable)userData;
```

**Parameters**

`[in] intermediateResultDelegate`: Callback function.  
`[in] userData`: Customized arguments passed to your function.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DynamsoftBarcodeReader *barcodeReader;
[barcodeReader setDBRIntermediateResultDelegate:self userData:nil];
```
2. 
```swift
barcodeReader.setDBRIntermediateResultDelegate(self, userData:nil)
```

## enableResultVerification

Enable **Result Verification** on the barcode results of video streaming barcode decoding. This feature is not enabled by default.

There are 2 way for you to get barcode results:

- From the return value of [`decode`](primary-decode.html) methods when processing a single image.
- From the [`textResultCallback`](protocol-dbrtextresultdelegate.html) when processing the video streaming.

**Result verification** feature only effects on the **OneD barcode** results you get from `textResultCallback`.

```objc
@property (nonatomic, assign) BOOL enableResultVerification;
```

**Parameters**

`boolean` value which stands for the target status of result verification mode.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[barcodeReader enableResultVerification:true];
// To check the status of this mode
[barcodeReader getEnableResultVerification]
```
2. 
```swift
barcodeReader.enableResultVerification = true
// To check the status of this mode
let x = barcodeReader.enableResultVerification
```

## enableDuplicateFilter

Filter out the duplicate results in the period of 3000ms for video barcode decoding. Barcode results with the same text and format will be returned only once during the period.

There are 2 way for you to get barcode results:

- From the return value of [`decode`](primary-decode.html) methods when processing a single image.
- From the [`textResultCallback`](protocol-dbrtextresultdelegate.html) when processing the video streaming.

**Duplicate filter** only effects on the duplicate results that output by `textResultCallback`.

```objc
@property (nonatomic, assign) BOOL enableDuplicateFilter;
```

**Parameters**

`boolean` value which stands for the target status of result duplicate filter mode.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[barcodeReader enableDuplicateFilter:true];
// To check the status of this mode
[barcodeReader getEnableDuplicateFilter]
```
2. 
```swift
barcodeReader.enableDuplicateFilter = true
// To check the status of this mode
let x = barcodeReader.enableDuplicateFilter
```
