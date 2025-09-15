---
layout: default-layout
title: DBRIntermediateResultDelegate - Dynamsoft Barcode Reader iOS API Reference
description: This page shows DBRIntermediateResultDelegate protocol of Dynamsoft Barcode Reader for iOS SDK.
keywords: DBRIntermediateResultDelegate, api reference, iOS
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
permalink: /programming/objectivec-swift/api-reference/protocol-dbrintermediateresultdelegate-v8.9.3.html
---

# DBRIntermediateResultDelegate

Represents the method to handle the intermediate result array returned by the library.

```objc
@protocol DBRIntermediateResultDelegate <NSObject>
```

| Method | Type | Description |
| ------ | ---- | ----------- |
| `intermediateResultCallback` | *required* | The method for users to add code for using intermediate results. |

## DBRIntermediateResultDelegate

The method for users to add code for using intermediate results.

```objc
@required
- (void)intermediateResultCallback:(NSInteger)frameId results:(NSArray<iIntermediateResult*>* _Nullable)results userData: (NSObject* _Nullable)userData;
```

**Parameters**

`frameID`: The ID of the frame.  
`results`: The intermediate results of the frame.  
`userData`: Arguments to pass to your function(s).
