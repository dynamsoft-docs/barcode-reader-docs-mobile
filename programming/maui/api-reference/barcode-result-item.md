---
layout: default-layout
title: BarcodeResultItem Class - Dynamsoft Barcode Reader MAUI Edition
description: BarcodeResultItem class represents a barcode result item decoded by barcode reader engine. It is derived from CapturedResultItem.
keywords: GetFormat, GetText, GetLocation, GetConfidence, GetModuleSize, BarcodeResultItem, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: BarcodeResultItem
---

# BarcodeResultItem Class

The `BarcodeResultItem` class represents a barcode result item decoded by the barcode reader. It is derived from [`CapturedResultItem`]({{ site.dcv_maui_api }}core/basic-structures/captured-result-item.html).

## Definition

*Namespace:* Dynamsoft.BarcodeReader.Maui

*Assembly:* Dynamsoft.BarcodeReader.Maui

```csharp
class BarcodeResultItem extends CapturedResultItem
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`Format`](#format) | *long* | Get the format of the barcode. |
| [`FormatString`](#formatstring) | *string* | Get the format text of the barcode. |
| [`Text`](#text) | *string* | Get the decode text of the barcode. |
| [`Bytes`](#bytes) | *byte[]* | Get the decode byte of the barcode. |
| [`Location`](#location) | *Quadrilateral* | Get the location of the barcode. |
| [`Confidence`](#confidence) | *int* | Get the confidence of the decoding result. |
| [`Angle`](#angle) | *int* | Get the rotation angle of the barcode. |
| [`ModuleSize`](#modulesize) | *int* | Get the module size of the barcode. |
| [`IsDPM`](#isdpm) | *bool* | Check whether the barcode is a DPM barcode. |
| [`IsMirrored`](#ismirrored) | *bool* | Check whether the barcode is mirrored. |

The following properties are inherited from class [`CapturedResultItem`]({{ site.dcv_maui_api }}core/captured-result-item.html).

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`Type`]({{ site.dcv_maui_api }}core/captured-result-item.html#type) | *[EnumCapturedResultItemType]({{ site.dcv_maui_api }}core/captured-result-item.html)* | Get the type of the captured result item. |
| [`TargetROIDefName`]({{ site.dcv_maui_api }}core/captured-result-item.html#targetroidefname) | *string* | The name of the [`TargetROIDef`]({{ site.dcv_parameters_reference }}target-roi-def/){:target="_blank"} object which includes a task that generated the result. |
| [`TaskName`]({{ site.dcv_maui_api }}core/captured-result-item.html#taskname) | *string* | The name of the task that generated the result. |

### Format

Get the format of the barcode. This format will be one of the [`EnumBarcodeFormat`]({{site.dbr_maui_api}}enum/barcode-format.html) items.

```csharp
long Format { get; }
```

### FormatString

Get the format of the barcode, but as text instead of a `BarcodeFormat` item.

```csharp
string FormatString { get; }
```

### Text

Get the raw decoded text of the barcode.

```csharp
string Text { get; }
```

### Bytes

Get the raw bytes of the decoded barcode text.

```csharp
byte[] Bytes { get; }
```

### Location

Get the location of the barcode as a [Quadrilateral]({{ site.dcv_maui_api }}core/quadrilateral.html). The quadrilateral contains the four vertex points of the location, with the first vertex being the left-most vertex, and going in a clockwise direction.

```csharp
Quadrilateral Location { get; }
```

### Confidence

Get the confidence of the decoded result, which is a measure of the result's accuracy. If the confidence is lower than 30, the result will not be output by default.

```csharp
int Confidence { get; }
```

### Angle

If the barcode is captured at an angle, this method returns the rotation angle of the barcode.

```csharp
int Angle { get; }
```

### ModuleSize

Get the module size of the barcode.

```csharp
int ModuleSize { get; }
```

### IsDPM

Tells you whether the barcode is a DPM barcode, which is a unique type of Datamatrix code.

```csharp
bool IsDPM { get; }
```

### IsMirrored

Check whether the barcode is mirrored.

```csharp
bool IsMirrored { get; }
```
