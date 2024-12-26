---
layout: default-layout
title: BarcodeScannerConfig Class - Dynamsoft Barcode Scanner Android Edition
description: BarcodeScannerConfig of DynamsoftBarcodeScanner Android is the class that defines the configurations for barcode scanning.
keywords: scanner, activity, startCapturing, license 
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: BarcodeScannerConfig
---

# BarcodeScannerConfig

`BarcodeScannerConfig` is the class that defines the configurations for barcode scanning. It is set via the input value of `BarcodeScannerActivity.ResultContract`

## Definition

*Assembly:* DynamsoftBarcodeReaderBundle.aar

*Namespace:* com.dynamsoft.dbrbundle.ui

```java
final class BarcodeScannerConfig
```

## Methods

| Method | Description |
| ------ | ----------- |
| [`setLicense`](#setlicense) | Set the license. |
| [`setTemplateFilePath`](#settemplatefilepath) | Set a path for the SDK to load template file. |
| [`setBarcodeFormats`](#setbarcodeformats) | Set the barcode formats to read. |
| [`setScanRegion`](#setscanregion) | Set a scan region. Only the barcodes located in the scan region can be decoded. |
| [`setTorchButtonVisible`](#settorchbuttonvisible) | Set whether to display the torch button when scanning. Uses can click the torch button to turn on/off the torch. |
| [`setBeepEnabled`](#setbeepenabled) | Set whether to trigger a beep sound when a barcode is detected. |
| [`setScanLaserVisible`](#setscanlaservisible) | Set whether to display a scan laser when scanning. |
| [`setAutoZoomEnabled`](#setautozoomenabled) | Set whether to enable the auto-zoom feature when scanning. |
| [`setCloseButtonVisible`](#setclosebuttonvisible) | Set whether to display a button for uses to close the scanner page. |
| [`getLicense`](#getlicense) | Returns the license string. |
| [`getTemplateFilePath`](#gettemplatefilepath) | Get the file path of the template file. |
| [`isTorchButtonVisible`](#istorchbuttonvisible) | Returns whether the button is visible. |
| [`getBarcodeFormats`](#getbarcodeformats) | Returns the barcode format settings. |
| [`getScanRegion`](#getscanregion) | Get the scan region. |
| [`isBeepEnabled`](#isbeepenabled) | Returns whether the beep sound is enabled. |
| [`isScanLaserVisible`](#isscanlaservisible) | Returns whether the scan laser is visible. |
| [`isAutoZoomEnabled`](#isautozoomenabled) | Returns whether the auto-zoom is enabled. |
| [`isCloseButtonVisible`](#isclosebuttonvisible) | Returns whether the close button is visible. |

### setLicense

Set the license.

```java
void setLicense(String license);
```

**Parameter(s)**

`license`: The license key to be used for initialization.

### setTemplateFilePath

Set a path for the SDK to load template file.

```java
void setTemplateFilePath(String templateFilePath);
```

**Parameter(s)**

`templateFilePath`: The path of the JSON template file.

### setBarcodeFormats

Set the barcode formats to read.

```java
void setBarcodeFormats(long format);
```

**Parameter(s)**

`format`: A combined value of `EnumBarcodeFormat` to specify which barcode format(s) the library should target.

### setScanRegion

Set a scan region. Only the barcodes located in the scan region can be decoded.

```java
void setScanRegion(DSRect scanRegion);
```

**Parameter(s)**

`scanRegion`: A `DSRect` object that specifies the scan region.

### setTorchButtonVisible

Set whether to display the torch button when scanning. Uses can click the torch button to turn on/off the torch.

```java
void setTorchButtonVisible(boolean torchButtonVisible);
```

**Parameter(s)**

`torchButtonVisible`: A boolean value that determines whether to display the torch button.

### setBeepEnabled

Set whether to trigger a beep sound when a barcode is detected.

```java
void setBeepEnabled(boolean beepEnabled);
```

**Parameter(s)**

`beepEnabled`: A boolean value that determines whether to enable the beep sound.

### setScanLaserVisible

Set whether to display a scan laser when scanning.

```java
void setScanLaserVisible(boolean scanLaserVisible);
```

**Parameter(s)**

`scanLaserVisible`: A boolean value that determines whether to display the scan laser.

### setAutoZoomEnabled

Set whether to enable the auto-zoom feature when scanning.

```java
void setAutoZoomEnabled(boolean autoZoomEnabled);
```

**Parameter(s)**

`autoZoomEnabled`: A boolean value that determines whether to enable the auto-zoom feature.

### setCloseButtonVisible

Set whether to display a button for uses to close the scanner page.

```java
void setCloseButtonVisible(boolean closeButtonVisible);
```

**Parameter(s)**

`closeButtonVisible`: A boolean value that determines whether to display the close button.

### getLicense

Returns the license string.

```java
String getLicense();
```

**Return Value**

The license key to be used for initialization.

### getTemplateFilePath

Get the file path of the template file.

```java
String getTemplateFilePath();
```

**Return Value**

The path of the JSON template file.

### getBarcodeFormats

Returns the barcode format settings.

```java
long getBarcodeFormats();
```

**Return Value**

A combined value of `EnumBarcodeFormat` to specify which barcode format(s) the library should target.

### getScanRegion

Get the scan region.

```java
DSRect getScanRegion();
```

**Return Value**

A `DSRect` object that specifies the scan region.

### isTorchButtonVisible

Returns whether the button is visible.

```java
boolean isTorchButtonVisible();
```

**Return Value**

A boolean value that determines whether the torch button is displayed.

### isBeepEnabled

Returns whether the beep sound is enabled.

```java
boolean isBeepEnabled();
```

**Return Value**

A boolean value that determines whether the beep sound is enabled.

### isScanLaserVisible

Returns whether the scan laser is visible.

```java
boolean isScanLaserVisible();
```

**Return Value**

A boolean value that determines whether the scan laser is displayed.

### isAutoZoomEnabled

Returns whether the auto-zoom is enabled.

```java
boolean isAutoZoomEnabled();
```

**Return Value**

A boolean value that determines whether the auto-zoom feature is enabled.

### isCloseButtonVisible

Returns whether the close button is visible.

```java
boolean isCloseButtonVisible();
```

**Return Value**

A boolean value that determines whether the close button is displayed.
