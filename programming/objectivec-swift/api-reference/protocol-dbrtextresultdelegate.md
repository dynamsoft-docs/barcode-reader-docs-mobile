---
layout: default-layout
title: DBRTextResultListener - Dynamsoft Barcode Reader iOS API Reference
description: This page shows DBRTextResultListener protocol of Dynamsoft Barcode Reader for iOS SDK.
keywords: DBRTextResultListener, api reference, iOS
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
multiProgrammingLanguage: true
enableLanguageSelection: true
ignore: true
permalink: /programming/objectivec-swift/api-reference/protocol-dbrtextresultdelegate.html
---

# DBRTextResultListener

The Protocol that handles callback when `TextResult` is returned by the library.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@protocol DBRTextResultListener <NSObject>
```
2. 
```swift
protocol DBRTextResultListener : NSObjectProtocol
```

| Method | Type | Description |
| ------ | ---- | ----------- |
| `textResultCallback` | *required* | Represents the method to handle the text result array returned by the library. |

## textResultCallback

Represents the method to handle the text result array returned by the library.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)textResultCallback:(NSInteger)frameId imageData:(iImageData *_Nonnull)imageData results:(NSArray<iTextResult*>* _Nullable)results;
```
2. 
```swift
func textResultCallback(_ frameId: Int, imageData: iImageData, results: [iTextResult]?)
```

**Parameters**

`frameID`: The ID of the frame.  
`imageData`: The image data of the frame.  
`results`: Recognized barcode results of the frame.

**Code Snippet**

You have to either use `DynamsoftCameraEnhacner` or `ImageSource` as the source of video streaming to receive barcode results from `textResultCallback`.

- View code snippet for how to decode with [`DynamsoftCameraEnhacner`](primary-video.html#setcameraenhancer)
- View code snippet for how to decode with [`ImageSource`](primary-video.html#setimagesource)
