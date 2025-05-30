---
layout: default-layout
title: BarcodeScannerConfig Class - Dynamsoft Barcode Reader MAUI Edition
description: BarcodeScannerConfig of DynamsoftBarcodeReader MAUI is the class that defines the configurations for Barcode scanning.
keywords: Barcode, scanner, config 
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: BarcodeScannerConfig
---

# BarcodeScannerConfig

`BarcodeScannerConfig` is the class that defines the configurations for Barcode scanning.

## Definition

*Assembly:* Dynamsoft.BarcodeReaderBundle.Maui

*Namespace:* Dynamsoft.BarcodeReaderBundle.Maui

```csharp
final class BarcodeScannerConfig
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`License`](#license) | *string* | Represents the license string. |
| [`TemplateFile`](#templatefile) | *string* | Represents the template with a file path or a JSON string. |
| [`IsTorchButtonVisible`](#istorchbuttonvisible) | *bool* | Represents the visibility status of the torch button. |
| [`IsBeepEnabled`](#isbeepenabled) | *bool* | Represents the play status of the beep sound when a Barcode is scanned. |
| [`IsCloseButtonVisible`](#isclosebuttonvisible) | *bool* | Represents the visibility status of the close button. |
| [`IsGuideFrameVisible`](#isguideframevisible) | *bool* | Represents the visibility status of the guide frame on the display. |
| [`IsCameraToggleButtonVisible`](#Iscameratogglebuttonvisible) | *bool* | Represents the visibility status of the camera toggle button. |
| [`ScanRegion`](#scanregion) | *DMRect?* | Represents the region to scan. |
| [`IsScanLaserVisible`](#isscanlaservisible) | *bool* | Represents the visibility status of the scan laser. |
| [`IsAutoZoomEnabled`](#isautozoomenabled) | *bool* | Represents the status of auto zoom. |
| [`BarcodeFormats`](#barcodeformats) | *EnumBarcodeFormat* | Represents the supported Barcode formats. |
| [`ScanningMode`](#scanningmode) | *EnumScanningMode* | Represents the scanning mode. |
| [`MaxConsecutiveStableFramesToExit`](#maxconsecutivestableframestoexit) | *int* | Represents the maximum number of consecutive stable frames to exit. |
| [`ExpectedBarcodesCount`](#expectedbarcodescount) | *int* | Represents the expected number of barcodes. |

### License

Represents the license string.

```csharp
string License { get; set; };
```

### TemplateFile

Represents the template with a file path or a JSON string.

```csharp
string? TemplateFile { get; set; };
```

### IsTorchButtonVisible

Represents the visibility status of the torch button.

```csharp
bool IsTorchButtonVisible { get; set; };
```

### IsBeepEnabled

Represents the play status of the beep sound when a Barcode is scanned.

```csharp
bool IsBeepEnabled { get; set; };
```

### IsCloseButtonVisible

Represents the visibility status of the close button.

```csharp
bool IsCloseButtonVisible { get; set; };
```

### IsCameraToggleButtonVisible

Represents the visibility status of the camera toggle button.

```csharp
bool IsCameraToggleButtonVisible { get; set; };
```

### ScanRegion

Represents the region to scan.

```csharp
DMRect? ScanRegion { get; set; };
```

### IsScanLaserVisible

Represents the visibility status of the scan laser.

```csharp
bool IsScanLaserVisible { get; set; };
```

### IsAutoZoomEnabled

Represents the status of auto zoom.

```csharp
bool IsAutoZoomEnabled { get; set; };
```

### BarcodeFormats

Represents the supported Barcode formats.

```csharp
EnumBarcodeFormat BarcodeFormats { get; set; };
```

### ScanningMode

Represents the scanning mode.

```csharp
EnumScanningMode ScanningMode { get; set; };
```

### MaxConsecutiveStableFramesToExit

Represents the maximum number of consecutive stable frames to exit.

```csharp
int MaxConsecutiveStableFramesToExit { get; set; };
```

### ExpectedBarcodesCount

Represents the expected number of barcodes.

```csharp
int ExpectedBarcodesCount { get; set; };
```
