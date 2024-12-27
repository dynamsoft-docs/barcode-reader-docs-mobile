---
layout: default-layout
title: License Activation - Dynamsoft Barcode Reader iOS Edition
description: Initialize the license of Dynamsoft Barcode Reader iOS edition.
keywords: license initialization, licensing
needAutoGenerateSidebar: true
---

# License Initialization

## Get a trial license

You can request a 30-day trial license via the [Request a Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=docs&package=mobile){:target="_blank"} link.

You can contact our support team via the [Contacting Us](https://www.dynamsoft.com/contact/){:target="_blank"} link when:

- You want request for an Offline trial license.
- Your license generation failed.

## Get a Full License

<a href="https://www.dynamsoft.com/company/contact" target="_blank">Contact us</a> to purchase a full license.

## Set the License In the Code

### For BarcodeScanner

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DSBarcodeScannerConfig *config = [[DSBarcodeScannerConfig alloc] init];
config.license = @"YOUR-LICENSE-KEY";
```
1. 
```swift
let config = BarcodeScannerConfig()
config.license = "YOUR-LICENSE-KEY"
```

### For Foundational Barcode Reader

The following shows how to set the license in the code.

<div class="sample-code-prefix template2"></div>
   >- Objective-C
   >- Swift
   >
> 
```objc
[DSLicenseManager initLicense:@"YOUR-LICENSE-KEY" verificationDelegate:self];
- (void)onLicenseVerified:(BOOL)isSuccess error:(nullable NSError *)error {
    if (!isSuccess && error != nil) {
        NSLog(@"error: %@", error);
    }
}
```
>
```swift
LicenseManager.initLicense("YOUR-LICENSE-KEY", verificationDelegate: self)
func onLicenseVerified(_ isSuccess: Bool, error: Error?) {
   if !isSuccess {
          if let error = error {
             print("\(error.localizedDescription)")
          }
   }
}
```
