---
layout: default-layout
title: DBRTextResultDelegate - Dynamsoft Barcode Reader iOS API Reference
description: This page shows DBRTextResultDelegate protocol of Dynamsoft Barcode Reader for iOS SDK.
keywords: DBRTextResultDelegate, api reference, iOS
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
permalink: /programming/objectivec-swift/api-reference/protocol-dbrtextresultdelegate-v8.9.3.html
---

# DBRTextResultDelegate

Represents the method to handle the text result array returned by the library.

```objc
@protocol DBRTextResultDelegate <NSObject>
```

| Method | Type | Description |
| ------ | ---- | ----------- |
| `textResultCallback` | *required* | The method for users to add code for using text results. |

## textResultCallback

The method for users to add code for using text results.

```objc
@required
- (void)textResultCallback:(NSInteger)frameId results:(NSArray<iTextResult*>* _Nullable)results userData: (NSObject* _Nullable)userData;
```

**Parameters**

`frameID`: The ID of the frame.  
`results`: Recognized barcode results of the frame.  
`userData`: Arguments to pass to your function(s).
