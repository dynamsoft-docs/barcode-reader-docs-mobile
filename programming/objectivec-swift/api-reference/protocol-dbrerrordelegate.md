---
layout: default-layout
title: DBRErrorDelegate - Dynamsoft Barcode Reader iOS API Reference
description: This page shows DBRErrorDelegate protocol of Dynamsoft Barcode Reader for iOS SDK.
keywords: DBRErrorDelegate, api reference, iOS
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
ignore: true
permalink: /programming/objectivec-swift/api-reference/protocol-dbrerrordelegate.html
---

# DBRErrorDelegate

Represents the method to handle the error code returned by the library when using frame decoding.

> Note:  
>
> - `DBRErrorDelegate` is deprecated in 9.0 version.

```objc
@protocol DBRErrorDelegate <NSObject>
```

| Method | Type | Description |
| ------ | ---- | ----------- |
| `errorCallback` | *required* | The method for users to add code for using error code. |

## errorCallback

The method for users to add code for using error code.

```objc
@required
- (void)errorCallback:(NSInteger)frameId errorCode:(NSInteger)errorCode userData: (NSObject* _Nullable)userData;
```

**Parameters**

`frameID`: The ID of the frame.  
`errorCode`: Error Code generated when decoding the frame.  
`userData`: Arguments to pass to your function(s).
