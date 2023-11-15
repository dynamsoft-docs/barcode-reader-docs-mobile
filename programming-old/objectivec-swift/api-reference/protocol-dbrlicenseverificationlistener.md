---
layout: default-layout
title: DBRLicenseVerificationListener - Dynamsoft Barcode Reader iOS API Reference
description: This page shows DBRLicenseVerificationListener protocol of Dynamsoft Barcode Reader for iOS SDK.
keywords: DBRLicenseVerificationListener, api reference, iOS
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
multiProgrammingLanguage: true
enableLanguageSelection: true
pageStartVer: 9.0
permalink: /programming/objectivec-swift/api-reference/protocol-dbrlicenseverificationlistener.html
---

# DBRLicenseVerificationListener

`DBRLicenseVerificationListener` is the protocol to handle license verification callback when using [`initLicense`](primary-license.html#initlicense).

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@protocol DBRLicenseVerificationListener <NSObject>
```
2. 
```swift
protocol DBRLicenseVerificationListener : NSObjectProtocol
```

| Method | Type | Description |
| ------ | ---- | ----------- |
| `DBRLicenseVerificationCallback` | *required* | The method for users to add code for license verification. |

## DBRLicenseVerificationCallback

The method for users to add code for license verification.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)DBRLicenseVerificationCallback:(bool)isSuccess error:(NSError * _Nullable)error;
```
2. 
```swift
func dbrLicenseVerificationCallback(_ isSuccess: Bool, error: Error?)
```

**Parameters**

`[in, out] isSuccess`: Whether the license verification was successful.  
`[in, out] error`: The error message from the license server.
