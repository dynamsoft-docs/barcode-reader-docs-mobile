---
layout: default-layout
title: BarcodeReader Parameter and Runtime Settings Basic Methods - Dynamsoft Barcode Reader Android API Reference
description: This page shows BarcodeReader basic runtime settings methods of Dynamsoft Barcode Reader for Android SDK.
keywords: setModeArgument, getModeArgument, getRuntimeSettings, updateRuntimeSettings, resetRuntimeSettings, parameter and runtime settings basic methods, BarcodeReader, api reference, android
needAutoGenerateSidebar: true
noTitleIndex: true
permalink: /programming/android/api-reference/primary-parameter-and-runtime-settings-basic.html
---


# Parameter and Runtime Settings Basic Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`getRuntimeSettings`](#getruntimesettings) | Get current runtime settings. |
  | [`updateRuntimeSettings(PublicRuntimeSettings)`](#updateruntimesettingspublicruntimesettings) | Modify and update the current runtime settings. |
  | [`updateRuntimeSettings(EnumPresetTemplate)`](#updateruntimesettingsenumpresettemplate) | Update runtime settings from one of the preset templates. |
  | [`resetRuntimeSettings`](#resetruntimesettings) | Reset runtime settings to default. |

  ---

## getRuntimeSettings

Get current settings and save them into a [`PublicRuntimeSettings`](auxiliary-PublicRuntimeSettings.html) struct.

```java
PublicRuntimeSettings getRuntimeSettings() throws BarcodeReaderException
```

**Return Value**

The [`PublicRuntimeSettings`](auxiliary-PublicRuntimeSettings.html) struct of template settings.

**Exceptions**

A [`BarcodeReaderException`](auxiliary-BarcodeReaderException.html) is thrown when:

- The library failed to get the current runtime settings.

**Code Snippet**

```java
BarcodeReader reader = new BarcodeReader();
PublicRuntimeSettings settings = reader.getRuntimeSettings();
```

## updateRuntimeSettings(PublicRuntimeSettings)

Update runtime settings with a given [`PublicRuntimeSettings`](auxiliary-PublicRuntimeSettings.html) struct.

```java
void updateRuntimeSettings(PublicRuntimeSettings settings) throws BarcodeReaderException
```

**Parameters**

`settings`: The [`PublicRuntimeSettings`](auxiliary-PublicRuntimeSettings.html) struct of template settings.

**Exceptions**

A [`BarcodeReaderException`](auxiliary-BarcodeReaderException.html) is thrown when:

- There exists parameters that are invalid or out of range.

**Code Snippet**

```java
BarcodeReader reader = new BarcodeReader();
PublicRuntimeSettings settings = reader.getRuntimeSettings();
settings.deblurLevel = 9;
reader.updateRuntimeSettings(settings);
```

## updateRuntimeSettings(EnumPresetTemplate)

Update the runtime settings from one of the preset templates.

```java
void updateRuntimeSettings(EnumPresetTemplate presetTemplate)
```

**Parameters**

`presetTemplate`: One of the preset templates defined by [EnumPresetTemplate]({{ site.mobile_enum }}preset-template.html?lang=android)

**Code Snippet**

```java
BarcodeReader reader = new BarcodeReader();
reader.updateRuntimeSettings(EnumPresetTemplate.VIDEO_SINGLE_BARCODE);
```

## resetRuntimeSettings

Reset all parameters to default values.

```java
void resetRuntimeSettings() throws BarcodeReaderException
```

**Exceptions**

A [`BarcodeReaderException`](auxiliary-BarcodeReaderException.html) is thrown when:

- The library failed to reset the runtime settings.

**Code Snippet**

```java
BarcodeReader reader = new BarcodeReader();
PublicRuntimeSettings settings = reader.getRuntimeSettings();
settings.deblurLevel = 9;
reader.updateRuntimeSettings(settings);
reader.resetRuntimeSettings();
```
