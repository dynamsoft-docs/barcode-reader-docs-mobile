---
layout: default-layout
title: DBRTextResultListener - Dynamsoft Barcode Reader iOS API Reference
description: This page shows DBRTextResultListener protocol of Dynamsoft Barcode Reader for iOS SDK.
keywords: DBRTextResultListener, api reference, iOS
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
permalink: /programming/objectivec-swift/api-reference/protocol-dbrtextresultdelegate-v9.0.2.html
---

# DBRTextResultListener

The Protocol that handles callback when `TextResult` is returned by the library.

```objc
@protocol DBRTextResultListener <NSObject>
```

| Method | Type | Description |
| ------ | ---- | ----------- |
| `textResultCallback` | *required* | Represents the method to handle the text result array returned by the library. |

## textResultCallback

Represents the method to handle the text result array returned by the library.

```objc
@required
- (void)textResultCallback:(NSInteger)frameId imageData:(iImageData *_Nonnull)imageData results:(NSArray<iTextResult*>* _Nullable)results;
```

**Parameters**

`frameID`: The ID of the frame.  
`imageData`: The image data of the frame.  
`results`: Recognized barcode results of the frame.

**Code Snippet**

You have to either use `DynamsoftCameraEnhacner` as the source of video streaming to receive barcode results from `textResultCallback`.

- View code snippet for how to decode with [`DynamsoftCameraEnhacner`](primary-video.html#setcameraenhancer)
