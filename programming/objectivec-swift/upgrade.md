---
layout: default-layout
title: How to Upgrade to 9.x- Dynamsoft Barcode Reader for iOS
description: Upgrade your Dynamsoft Barcode Reader SDK from 7.x, 8.x to 9.x along with its license activation code, decoding code, and default settings for iOS.
keywords: How to upgrade, objective-c, oc, swift
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
multiProgrammingLanguage: true
enableLanguageSelection: true
pageStartVer: 9.0
---

# How to Upgrade to 9.x

## From Version 8.x to 9.x

### Update the SDK to 9.x Version

- Local Dependency
  - If you are referencing only `DynamsoftBarcodeReader` SDK, replace the old `DynamsoftBarcodeReader.framework` file with the latest version.

  - If you are referencing both `DynamsoftBarcodeReader` and `DynamsoftCameraEnhancer` SDK, please replace the old `DynamsoftBarcodeReader.framework` and `DynamsoftCameraEnhancer.framework` files with the latest version.

- Remote Dependency(Cocopods)
  - If you are referencing only `DynamsoftBarcodeReader` SDK, update the version of `DynamsoftBarcodeReader` to the latest version in the `Podfile`.
    >Note: Please replace {version-number} with the correct version number.
    >- pod `DynamsoftBarcodeReader', '{version-number}'

  - If you are referencing both `DynamsoftBarcodeReader` and `DynamsoftCameraEnhancer` SDK, update the version of `DynamsoftBarcodeReader` and `DynamsoftCameraEnhancer` to the latest version in the `Podfile`.
    >Note: Please replace {version-number} with the correct version number.
    >- pod `DynamsoftCameraEnhancer', '{version-number}'
    >- pod `DynamsoftBarcodeReader', '{version-number}'

### Update the License Activation Code

Starting with 9.0, we unify the API for setting offline and online licenses.

code in 8.x:

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
barcodeReader = [[DynamsoftBarcodeReader alloc] initWithLicense:@"An offline license"];
iDMDLSConnectionParameters* dls = [[iDMDLSConnectionParameters alloc] init];
dls.organizationID = @"Your organization Id";
_barcodeReader = [[DynamsoftBarcodeReader alloc] initLicenseFromDLS:dls verificationDelegate:self];
- (void)DLSLicenseVerificationCallback:(bool)isSuccess error:(NSError * _Nullable)error{}
```
2. 
```swift
let barcodeReader = DynamsoftBarcodeReader.init(license: "An offline license")let dls = iDMDLSConnectionParameters()
dls.organizationID = "Your organization Id"
barcodeReader = DynamsoftBarcodeReader(licenseFromDLS: dls, verificationDelegate: self)
func DLSLicenseVerificationCallback(_ isSuccess: Bool, error: Error?){}
```

Please replace your license activation code with the following code. You can get the `3.0 license` from [customer portal-->License detail](https://www.dynamsoft.com/customer/index){:target="_blank"}.

code in 9.x:

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[DynamsoftBarcodeReader initLicense:@"Put your license here" verificationDelegate: self];
- (void)DBRLicenseVerificationCallback:(bool)isSuccess error:(NSError *)error{}
```
2. 
```swift
DynamsoftBarcodeReader.initLicense("Put your license here", verificationDelegate: self)
func dbrLicenseVerificationCallback(_ isSuccess: Bool, error: Error?) {}
```

> Note:  
>  
> 1.The following license activation method are removed, you should make the changes in 9.x upgrade:
> - `initLicenseFromLTS`
>
> 2.The following license activation methods are deprecated, they will be removed in version 10.0. We recommend that you upgrade to the new license API, but this is optional during the upgrade to 9.x:
>  
> - `initLicenseFromDLS`
> - `initLicenseFromServer`

### Update the default runtime settings

In 9.0, the default preset template `EnumPresetTemplate.default` will be changed to `EnumPresetTemplate.videoSingleBarcode` internally to better suit mobile scenarios. We also added template `EnumPresetTemplate.imageDefault` to store the legacy configurations of `EnumPresetTemplate.default`.

If the default template is not specified in the previous code (the default template is still used internally) or the default template is used explicitly, and you want to keep the original running logic, you need to call the following function after creating the barcode reader instance:

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DynamsoftBarcodeReader* barcodereader = [[DynamsoftBarcodeReader alloc] init];
// add the following code to change to the legacy default settings
[barcodereader updateRuntimeSettings:EnumPresetTemplateImageDefault];
// change the settings based on the legacy default template...
```
2. 
```swift
let barcodereader = DynamsoftBarcodeReader()
// add the following code to change to the legacy default settings
barcodereader.updateRuntimeSettings(EnumPresetTemplate.imageDefault)
// change the settings based on the legacy default template...
```

### Update the Video Barcode Decoding Code

Some of the legacy video barcode decoding methods are removed, we recommend you to review our sample code and re-write the barcode scanning module. Make sure to change your code if you were using the following APIs:

- Legacy Video Decoding APIs:
  - `interface iFrameDecodingParameters`
  - `protocol DBRErrorDelegate`
  - `DynamsoftBarcodeReader.startFrameDecoding`
  - `DynamsoftBarcodeReader.startFrameDecodingEx`
  - `DynamsoftBarcodeReader.appendFrame`
  - `DynamsoftBarcodeReader.setDBRErrorDelegate`
  - `DynamsoftBarcodeReader.stopFrameDecoding`
  - `DynamsoftBarcodeReader.getFrameDecodingParameters`
  - `DynamsoftBarcodeReader.getLengthOfFrameQueue`

- Legacy Camera Enhancer supporting APIs
  - interfance `iDCESettingParameters`
  - `DynamsoftBarcodeReader.setCameraEnhancerPara`

> Note:  
>
> If you are upgrading from v8.9.0 or higher versions, you might not need to make any changes on video barcode decoding APIs.

### Update Swift Code

We made quit a lot of changes on the Swift APIs in 9.0 version. Please check the API documents for the details if you are using the following APIs.

- Modified Swift APIs:
  - `DynamsoftBarcodeReader.decodeImage`
  - `DynamsoftBarcodeReader.decodeFileWithName`
  - `DynamsoftBarcodeReader.decodeBase64`
  - `DynamsoftBarcodeReader.decodeBuffer`
  - `DynamsoftBarcodeReader.getRuntimeSettings`
  - `DynamsoftBarcodeReader.updateRuntimeSettings`(with parameter `iPublicRuntimeSettings`)
  - `DynamsoftBarcodeReader.initRuntimeSettingsWithFile`
  - `DynamsoftBarcodeReader.initRuntimeSettingsWithString`
  - `DynamsoftBarcodeReader.appendTplFileToRuntimeSettings`
  - `DynamsoftBarcodeReader.appendTplStringToRuntimeSettings`
  - `DynamsoftBarcodeReader.resetRuntimeSettings`
  - `DynamsoftBarcodeReader.outputSettingsToString`
  - `DynamsoftBarcodeReader.outputSettingsToFile`
  - `DynamsoftBarcodeReader.allParameterTemplateNames`
  - `DynamsoftBarcodeReader.getModeArgument`
  - `DynamsoftBarcodeReader.setModeArgument`
  - `DynamsoftBarcodeReader.getIntermediateResult`
  - `DynamsoftBarcodeReader.createIntermediateResult`
  - `DynamsoftBarcodeReader.decodeIntermediateResult`


## From version 7.x to 9.x

We made some structural updates in the new version. To upgrade from 7.x to 9.x, we recommend you to review our sample code and re-write the barcode scanning module.
