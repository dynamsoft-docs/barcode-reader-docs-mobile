---
layout: default-layout
title: DMDLSLicenseVerificationDelegate - Dynamsoft Barcode Reader iOS API Reference
description: This page shows DMDLSLicenseVerificationDelegate protocol of Dynamsoft Barcode Reader for iOS SDK.
keywords: DMDLSLicenseVerificationDelegate, api reference, iOS
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
pageStartVer: 8.4
ignore: true
permalink: /programming/objectivec-swift/api-reference/protocol-dmdlslicenseverificationdelegate.html
---

# DMDLSLicenseVerificationDelegate

`DMDLSLicenseVerificationDelegate` is the protocol to handle license verification callback when using `initLicenseFromDLS`.

> Note:  
>  
> - `initLicenseFromDLS` and `DMDLSLicenseVerificationDelegate` are deprecated and will be removed in 10.0 version release.  
> - Please use [`initLicense`](primary-license.html#initlicense) and [`DBRLicenseVerificationListener`](protocol-dbrlicenseverificationlistener.html) to initialize and verify the license for 9.x versions.

```objc
@protocol DMDLSLicenseVerificationDelegate <NSObject>
```

| Method | Type | Description |
| ------ | ---- | ----------- |
| `DLSLicenseVerificationCallback` | *required* | The method for users to add code for license verification. |

## DLSLicenseVerificationCallback

The method for users to add code for license verification.

```objc
@required
- (void)DLSLicenseVerificationCallback:(bool)isSuccess error:(NSError * _Nullable)error;
```

**Parameters**

`[in, out] isSuccess`: Whether the license verification was successful.  
`[in, out] error`: The error message from the license server.
