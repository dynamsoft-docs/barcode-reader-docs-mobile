---
layout: default-layout
title: Result Methods - Dynamsoft Barcode Reader iOS API Reference
description: This page shows Result methods of Dynamsoft Barcode Reader for iOS SDK.
keywords: getIntermediateResult, result methods, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
noTitleIndex: true
permalink: /programming/objectivec-swift/api-reference/primary-result.html
---

# IntermediateResult Decoding Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`createIntermediateResult`](#createintermediateresult) | Inits an intermediateResult struct with default values. |
  | [`getIntermediateResult`](#getintermediateresult) | Get intermediate results. |
  | [`decodeIntermediateResults`](#decodeintermediateresults) | Decodes barcode from intermediate results. |

  ---

## createIntermediateResult

Inits an intermediateResult struct with default values.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (iIntermediateResult* _Nullable)createIntermediateResult:(EnumIntermediateResultType)type
                                                     error:(NSError* _Nullable * _Nullable)error;
```
2. 
```swift
func createIntermediateResult(_ type: EnumIntermediateResultType) throws -> iIntermediateResult
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

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(NSArray<iIntermediateResult*>* _Nullable)getIntermediateResult:(NSError* _Nullable *  _Nullable)error;
```
2. 
```swift
func getIntermediateResult() throws -> [iIntermediateResult]
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

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (NSArray<iTextResult*>* _Nullable)decodeIntermediateResults:(NSArray<iIntermediateResult*>* _Nullable)array
                                                        error:(NSError* _Nullable * _Nullable)error;
```
2. 
```swift
func decodeIntermediateResults(_ array: [iIntermediateResult]?) throws -> [iTextResult]
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
