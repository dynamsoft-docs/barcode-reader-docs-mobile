---
layout: default-layout
title: DMLTSLicenseVerificationDelegate - Dynamsoft Barcode Reader iOS API Reference
description: This page shows DMLTSLicenseVerificationDelegate protocol of Dynamsoft Barcode Reader for iOS SDK.
keywords: DMLTSLicenseVerificationDelegate, api reference, iOS
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
pageStartVer: 8.4
permalink: /programming/objectivec-swift/api-reference/protocol-dmdlslicenseverificationdelegate-v8.4.0.html
---

# DMLTSLicenseVerificationDelegate

The callback of the license server.

```objc
@protocol DMLTSLicenseVerificationDelegate <NSObject>
```

| Method | Type | Description |
| ------ | ---- | ----------- |
| `LTSLicenseVerificationCallback` | *required* | The method for users to add code for license verification. |

## LTSLicenseVerificationCallback

The method for users to add code for license verification.

```objc
@required
- (void)LTSLicenseVerificationCallback:(bool)isSuccess error:(NSError * _Nullable)error;
```

**Parameters**

`[in, out] isSuccess`: Whether the license verification was successful.  
`[in, out] error`: The error message from the license server.
