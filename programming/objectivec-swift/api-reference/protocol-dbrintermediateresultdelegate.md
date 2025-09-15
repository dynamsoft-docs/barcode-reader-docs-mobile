---
layout: default-layout
title: DBRIntermediateResultListener - Dynamsoft Barcode Reader iOS API Reference
description: This page shows DBRIntermediateResultListener protocol of Dynamsoft Barcode Reader for iOS SDK.
keywords: DBRIntermediateResultListener, api reference, iOS
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
multiProgrammingLanguage: true
enableLanguageSelection: true
ignore: true
permalink: /programming/objectivec-swift/api-reference/protocol-dbrintermediateresultdelegate.html
---

# DBRIntermediateResultListener

The Protocol that handles callback when `IntermediateResult` is returned by the library.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@protocol DBRIntermediateResultListener <NSObject>
```
2. 
```swift
protocol DBRIntermediateResultListener : NSObjectProtocol
```

| Method | Type | Description |
| ------ | ---- | ----------- |
| `intermediateResultCallback` | *required* | Represents the method to handle the intermediate result array returned by the library. |

## intermediateResultCallback

Represents the method to handle the intermediate result array returned by the library.



<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)intermediateResultCallback:(NSInteger)frameId imageData:(iImageData *_Nonnull)imageData results:(NSArray<iIntermediateResult*>* _Nullable)results;
```
2. 
```swift
func intermediateResultCallback(_ frameId: Int, imageData: iImageData, results: [iIntermediateResult]?)
```

**Parameters**

`frameID`: The ID of the frame.  
`imageData`: The image data of the frame.  
`results`: The intermediate results of the frame.
