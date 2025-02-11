---
layout: default-layout
title: BarcodeScannerConfig Class - Dynamsoft Barcode Reader Android Edition
description: BarcodeScannerConfig of Dynamsoft Barcode Reader Android is the class that defines the configurations for BarcodeScanner component.
keywords: scanner, activity, startCapturing, license 
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: BarcodeScannerConfig
---

# BarcodeScannerConfig

`BarcodeScannerConfig` is the class that defines the configurations for barcode scanning. Once the `BarcodeScannerConfig` object is made, it is set via the `BarcodeScannerActivity.ResultContract`.

## Definition

*Assembly:* DynamsoftBarcodeReaderBundle.aar

*Namespace:* com.dynamsoft.dbrbundle.ui

```java
final class BarcodeScannerConfig
```

## Methods

| Method | Description |
| ------ | ----------- |
| [`setLicense`](#setlicense) | Sets the license key for the Barcode Reader. |
| [`setTemplateFilePath`](#settemplatefilepath) | Sets the parameters template for the Barcode Reader via a local JSON file path. |
| [`setBarcodeFormats`](#setbarcodeformats) | Sets the barcode format(s) to read. |
| [`setScanRegion`](#setscanregion) | Sets a scan region where only the barcodes located in the scan region can be decoded. |
| [`setTorchButtonVisible`](#settorchbuttonvisible) | Sets whether to display the torch button when scanning or not. |
| [`setBeepEnabled`](#setbeepenabled) | Sets whether to trigger a beep sound when a barcode is detected. |
| [`setScanLaserVisible`](#setscanlaservisible) | Sets whether to display a scan laser when scanning. |
| [`setAutoZoomEnabled`](#setautozoomenabled) | Sets whether to enable the auto-zoom feature when scanning. |
| [`setCloseButtonVisible`](#setclosebuttonvisible) | Sets whether to display a button that can close the scanner page. |
| [`getLicense`](#getlicense) | Returns the license key string. |
| [`getTemplateFilePath`](#gettemplatefilepath) | Returns the file path of the template file if one is being used. |
| [`isTorchButtonVisible`](#istorchbuttonvisible) | Returns whether the button is visible. |
| [`getBarcodeFormats`](#getbarcodeformats) | Returns the barcode format(s) that the library will accept. |
| [`getScanRegion`](#getscanregion) | Returns the scan region. |
| [`isBeepEnabled`](#isbeepenabled) | Returns whether the beep sound is enabled. |
| [`isScanLaserVisible`](#isscanlaservisible) | Returns whether the scan laser is visible. |
| [`isAutoZoomEnabled`](#isautozoomenabled) | Returns whether the auto-zoom feature is enabled. |
| [`isCloseButtonVisible`](#isclosebuttonvisible) | Returns whether the close button is visible. |

### setLicense

Sets the license key for the Barcode Reader.

```java
void setLicense(String license);
```

**Parameter(s)**

`license`: The license key to be used for initialization.

### setTemplateFilePath

Sets the local JSON file path that will configure the parameters template for the Barcode Reader.

```java
void setTemplateFilePath(String templateFilePath);
```

**Parameter(s)**

`templateFilePath`: The path of the JSON template file.

### setBarcodeFormats

Sets the barcode format(s) to read.

```java
void setBarcodeFormats(long format);
```

**Parameter(s)**

`format`: A combined value of [`EnumBarcodeFormat`]({{ site.dcvb_enumerations }}barcode-reader/barcode-format.html?lang=android) to specify which barcode format(s) the library should target.

### setScanRegion

Sets a scan region. Only the barcodes located in the scan region can be decoded.

```java
void setScanRegion(DSRect scanRegion);
```

**Parameter(s)**

`scanRegion`: A [`DSRect`]({{ site.dcvb_android_api }}core/basic-structures/rect.html) object that specifies the scan region.

### setTorchButtonVisible

Sets whether to display the torch button when scanning. User can click the torch button to turn on/off the torch.

```java
void setTorchButtonVisible(boolean torchButtonVisible);
```

**Parameter(s)**

`torchButtonVisible`: A boolean value that determines whether to display the torch button.

### setBeepEnabled

Sets whether to trigger a beep sound when a barcode is detected.

```java
void setBeepEnabled(boolean beepEnabled);
```

**Parameter(s)**

`beepEnabled`: A boolean value that determines whether to enable the beep sound.

### setScanLaserVisible

Sets whether to display a scan laser when scanning.

```java
void setScanLaserVisible(boolean scanLaserVisible);
```

**Parameter(s)**

`scanLaserVisible`: A boolean value that determines whether to display the scan laser.

### setAutoZoomEnabled

Sets whether to enable the auto-zoom feature when scanning.

```java
void setAutoZoomEnabled(boolean autoZoomEnabled);
```

**Parameter(s)**

`autoZoomEnabled`: A boolean value that determines whether to enable the auto-zoom feature.

### setCloseButtonVisible

Sets whether to display a button that can close the scanner page.

```java
void setCloseButtonVisible(boolean closeButtonVisible);
```

**Parameter(s)**

`closeButtonVisible`: A boolean value that determines whether to display the close button.

### getLicense

Returns the license key string.

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

A combined value of [`EnumBarcodeFormat`]({{ site.dcvb_enumerations }}barcode-reader/barcode-format.html?lang=android) to specify which barcode format(s) the library should target.

### getScanRegion

Returns the scan region.

```java
DSRect getScanRegion();
```

**Return Value**

A [`DSRect`]({{ site.dcvb_android_api }}core/basic-structures/rect.html) object that specifies the scan region.

### isTorchButtonVisible

Returns a boolean indicating whether or not the torch button is visible.

```java
boolean isTorchButtonVisible();
```

**Return Value**

A boolean value that determines whether the torch button is displayed.

### isBeepEnabled

Returns a boolean indicating whether or not the beep sound is enabled.

```java
boolean isBeepEnabled();
```

**Return Value**

A boolean value that determines whether the beep sound is enabled.

### isScanLaserVisible

Returns a boolean indicating whether or not the scan laser is visible.

```java
boolean isScanLaserVisible();
```

**Return Value**

A boolean value that determines whether the scan laser is displayed.

### isAutoZoomEnabled

Returns a boolean indicating whether or not the auto-zoom feature is enabled.

```java
boolean isAutoZoomEnabled();
```

**Return Value**

A boolean value that determines whether the auto-zoom feature is enabled.

### isCloseButtonVisible

Returns a boolean indicating whether or not the close button is visible.

```java
boolean isCloseButtonVisible();
```

**Return Value**

A boolean value that determines whether the close button is displayed.
