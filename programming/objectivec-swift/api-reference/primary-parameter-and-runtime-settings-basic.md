---
layout: default-layout
title: Parameter and Runtime Settings Basic Methods - Dynamsoft Barcode Reader iOS API Reference
description: This page shows basic Runtime Settings methods of Dynamsoft Barcode Reader for iOS SDK.
keywords: setModeArgument, getModeArgument, getRuntimeSettings, updateRuntimeSettings, resetRuntimeSettings, parameter and runtime settings basic methods, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
noTitleIndex: true
permalink: /programming/objectivec-swift/api-reference/primary-parameter-and-runtime-settings-basic.html
---

# Parameter and Runtime Settings Basic Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`getRuntimeSettings`](#getruntimesettings) | Get current runtime settings. |
  | [`updateRuntimeSettings:(iPublicRuntimeSettings)`](#updateruntimesettingsipublicruntimesettings) | Update runtime settings with a given struct. |
  | [`updateRuntimeSettings:(EnumPresetTemplate)`](#updateruntimesettingsenumpresettemplate) | Update runtime settings from one of the preset templates. |
  | [`resetRuntimeSettings`](#resetruntimesettings) | Resets all parameters to default values. |

---

## getRuntimeSettings

Get current settings and save them into a [`iPublicRuntimeSettings`](auxiliary-iPublicRuntimeSettings.md) struct.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (iPublicRuntimeSettings* _Nullable)getRuntimeSettings:(NSError* _Nullable * _Nullable)error;
```
2. 
```swift
func getRuntimeSettings() throws -> iPublicRuntimeSettings
```

**Parameters**

`[in,out] error`: A pointer to an error object.

An error occurs when:

- The library failed to get the runtime settings.

**Return Value**

A DBRPublicRuntimeSettings storing current runtime settings.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSError __autoreleasing * _Nullable error;
[barcodeReader getRuntimeSettings:&error];
```
2. 
```swift
let settings = try? barcodeReader.getRuntimeSettings()
```

## updateRuntimeSettings:(iPublicRuntimeSettings*)

Update runtime settings with a given [`iPublicRuntimeSettings`](auxiliary-iPublicRuntimeSettings.md) struct.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (BOOL)updateRuntimeSettings:(iPublicRuntimeSettings* _Nonnull)settings
                        error:(NSError* _Nullable * _Nullable)error
                        NS_SWIFT_NAME(updateRuntimeSettings(_:));
```
2. 
```swift
func updateRuntimeSettings(_ settings: iPublicRuntimeSettings) throws
```

**Parameters**

`[in] settings` The struct of template settings.  
`[in,out] error`: A pointer to an error object.

An error occurs when:

- There exists parameters that are invalid or out of range in the `iPublicRuntimeSettings` object.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
iPublicRuntimeSettings *settings = [barcodeReader getRuntimeSettings:nil];
// After you have made some changes on the runtime settings.
[barcodeReader updateRuntimeSettings:settings error:nil];
```
2. 
```swift
let settings = try? barcodeReader.getRuntimeSettings()
// After you have made some changes on the runtime settings.
try? barcodeReader.updateRuntimeSettings(settings!)
```

## updateRuntimeSettings:(EnumPresetTemplate)

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)updateRuntimeSettings:(EnumPresetTemplate)presetTemplate;
```
2. 
```swift
func updateRuntimeSettings(_ tpl: EnumPresetTemplate)
```

**Parameters**

`presetTemplate`: One of the preset templates defined by [EnumPresetTemplate]({{ site.mobile_enum }}preset-template.html?lang=objc,swift)

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[barcodeReader updateRuntimeSettings:EnumPresetTemplateVideoSingleBarcode];
```
2. 
```swift
barcodeReader.updateRuntimeSettings(EnumPresetTemplate.videoSingleBarcode)
```

## resetRuntimeSettings

Reset all parameters to default values.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (BOOL)resetRuntimeSettings:(NSError* _Nullable * _Nullable)error;
```
2. 
```swift
func resetRuntimeSettings() throws
```

**Parameters**

`[in,out] error` Input a pointer to an error object. If an error occurs, this pointer is set to an actual error object containing the error information. You may specify nil for this parameter if you do not want the error information.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[barcodeReader resetRuntimeSettings:nil];
```
2. 
```swift
try? barcodeReader.resetRuntimeSettings()
```
