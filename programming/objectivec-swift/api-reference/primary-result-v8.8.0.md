---
layout: default-layout
title: Result Methods - Dynamsoft Barcode Reader iOS API Reference
description: This page shows Result methods of Dynamsoft Barcode Reader for iOS SDK.
keywords: getIntermediateResult, result methods, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
noTitleIndex: true
multiProgrammingLanguage: true
enableLanguageSelection: true
permalink: /programming/objectivec-swift/api-reference/primary-result.html
---

# IntermediateResult Decoding Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`createIntermediateResult`](#createintermediateresult) | Inits an intermediateResult struct with default values. |
  | [`getIntermediateResult`](#getintermediateresult) | Get intermediate results. |
  | [`decodeIntermediateResults`](#decodeintermediateresults) | Decodes barcode from intermediate results. |
  | [`enableResultVerification`](#enableresultverification) | Enable **Result Verification** feature to improve the accuracy of barcode results for video streaming barcode decoding. |
  | [`enableDuplicateFilter`](#enableduplicatefilter) | Enable **Duplicate Filter** feature to filter out the duplicate results in the period of 3000ms for video barcode decoding. |

  ---

## createIntermediateResult

Inits an intermediateResult struct with default values.

```objc
- (iIntermediateResult* _Nullable)createIntermediateResult:(EnumIntermediateResultType)type
                                                     error:(NSError* _Nullable * _Nullable)error;
```

**Parameters**

`[in] type`: The intermediate result type ([EnumIntermediateResultType]({{ site.mobile_enum }}intermediate-result-type.html?lang=objc,swift)) to initialize.  
`[in,out] error`: A pointer to an error object.

An error occurs when:

- Your license key doesn't include the intermediate result item.

**Return Value**

An [`iIntermediateResult`](auxiliary-iIntermediateResult.md) struct with default values.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSError __autoreleasing * _Nullable error;
iIntermediateResult *irResult;
irResult = [barcodeReader createIntermediateResult:EnumIntermediateResultTypeOriginalImage error:&error];
```
2. 
```swift
var irResult:iIntermediateResult!
irResult = try? barcodeReader.createIntermediateResult(EnumIntermediateResultType(rawValue: EnumIntermediateResultType.originalImage.rawValue)!)
```

## getIntermediateResult

Return intermediate results containing the original image, the color clustered image, the binarized image, contours, lines, text blocks, etc.

```objc
-(NSArray<iIntermediateResult*>* _Nullable)getIntermediateResult:(NSError* _Nullable *  _Nullable)error;
```

**Parameters**

`[in,out] error` Input a pointer to an error object. If an error occurs, this pointer is set to an actual error object containing the error information. You may specify nil for this parameter if you do not want the error information.

**Return Value**

Returns an [`iIntermediateResult`](auxiliary-iIntermediateResult.md) array.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
iPublicRuntimeSettings *settings;
NSArray<iTextResult *> *result;
NSArray<iIntermediateResult *> *irResult;
[_barcodeReader getRuntimeSettings:nil];
settings.intermediateResultTypes = EnumIntermediateResultTypeColourConvertedGrayScaleImage|EnumIntermediateResultTypeOriginalImage|EnumIntermediateResultTypeColourClusteredImage;
[_barcodeReader updateRuntimeSettings:settings error:nil];
result = [_barcodeReader decodeFileWithName:@"your file path" error:nil];
irResult = [_barcodeReader getIntermediateResult:&error];
```
2. 
```swift
let settings = try? barcodeReader.getRuntimeSettings()
settings.intermediateResultTypes = EnumIntermediateResultType.ColourConvertedGrayScaleImage.rawValue | EnumIntermediateResultType.OriginalImage.rawValue | EnumIntermediateResultType.ColourClusteredImage.rawValue
barcodeReader.updateRuntimeSettings(settings)
let result = try? barcodeReader.decodeFileWithName("your file path", templateName:"")
let irResult = try? barcodeReader.getIntermediateResult()
```

## decodeIntermediateResults

Decodes barcode from intermediate results.

```objc
- (NSArray<iTextResult*>* _Nullable)decodeIntermediateResults:(NSArray<iIntermediateResult*>* _Nullable)array
                                                        error:(NSError* _Nullable * _Nullable)error
                                                        NS_SWIFT_NAME(decodeIntermediateResults(_:));
```

**Parameters**

`[in] array`: The intermediate result array for decoding.  
`[in,out] error`: A pointer to an error object.

An error occurs when:

- The library failed to read the image.

**Return Value**

The [`iTextResult`](auxiliary-iTextResult.md) of each successfully decoded barcode.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSError __autoreleasing * _Nullable error;
[barcodeReader getRuntimeSettings:&error];
settings.intermediateResultTypes = EnumIntermediateResultTypeOriginalImage | EnumIntermediateResultTypeTypedBarcodeZone;
settings.intermediateResultSavingMode = EnumIntermediateResultSavingModeMemory;
[barcodeReader updateRuntimeSettings:settings error:&error];
NSArray<iTextResult*>* resultByFile = [barcodeReader decodeFileWithName:@"your file path" error:&error];
NSArray<iIntermediateResult*>* array = [barcodeReader getIntermediateResult:&error];
NSArray<iTextResult*>* result = [barcodeReader decodeIntermediateResults:array error:&error];
```
2. 
```swift
let result:[iTextResult]?
let settings = try? barcodeReader.getRuntimeSettings()
settings.intermediateResultTypes = EnumIntermediateResultType.originalImage.rawValue | EnumIntermediateResultType.typedBarcodeZone.rawValue
settings.intermediateResultSavingMode = .memory
try? barcodeReader.updateRuntimeSettings(settings)
result = try? barcodeReader.decodeFilewithName("your file path")
let intermediateResult = try? barcodeReader.getIntermediateResult()
result = try? barcodeReader.decodeIntermediateResults(intermediateResult)
```

## enableResultVerification

Enable **Result Verification** on the barcode results of video streaming barcode decoding. This feature is not enabled by default.

There are 2 way for you to get barcode results:

- From the return value of [`decode`](primary-decode.md) methods when processing a single image.
- From the [`textResultCallback`](interface-textresultcallback.md) when processing the video streaming.

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

- From the return value of [`decode`](primary-decode.md) methods when processing a single image.
- From the [`textResultCallback`](protocol-dbrtextresultdelegate.md) when processing the video streaming.

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
