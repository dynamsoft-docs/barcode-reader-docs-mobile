---
layout: default-layout
title: BarcodeResultItem Class - Dynamsoft Barcode Reader Android Edition
description: BarcodeResultItem class represents a barcode result item decoded by barcode reader engine. It is derived from CapturedResultItem.
keywords: GetFormat, GetText, GetLocation, GetConfidence, GetModuleSize, BarcodeResultItem, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: BarcodeResultItem
permalink: /programming/android/api-reference/barcode-result-item.html
---

# BarcodeResultItem Class

The `BarcodeResultItem` class represents a barcode result item decoded by barcode reader engine. It is derived from `CCapturedResultItem`.

## Definition

*Namespace:* dynamsoft::dbr

*Assembly:* DynamsoftBarcodeReader

*Inheritance:* [CCapturedResultItem]({{ site.dcv_android_api }}core/basic-structures/captured-result-item.html) -> BarcodeResultItem

```cpp
class BarcodeResultItem : public CCapturedResultItem
```

## Methods

| Method               | Description |
|----------------------|-------------|
| [`GetFormat`](#getformat) | Gets the format of the decoded barcode result. |
| [`GetFormatString`](#getformatstring) | Gets the format string of the decoded barcode result. |
| [`GetText`](#gettext) | Gets the text result of the decoded barcode. |
| [`GetBytes`](#getbytes) | Gets the text bytes of the decoded barcode result. |
| [`GetBytesLength`](#getbyteslength) | Gets the text length of the decoded barcode result. |
| [`GetLocation`](#getlocation) | Gets the location of the decoded barcode in a quadrilateral. |
| [`GetConfidence`](#getconfidence) | Gets the confidence of the decoded barcode result. |
| [`GetAngle`](#getangle) | Gets the angle of the decoded barcode result. |
| [`GetModuleSize`](#getmodulesize) | Gets the module size of the decoded barcode result. |
| [`GetDetails`](#getdetails) | Gets the details of the decoded barcode result. |
| [`IsDPM`](#isdpm) | Gets whether the decoded barcode is a DPM code. |
| [`IsMirrored`](#ismirrored) | Gets whether the decoded barcode is a mirrored barcode. |
| [`GetRotationTransformMatrix`](#getrotationtransformmatrix) | Gets the rotation transform matrix of the decoded barcode result. |


### GetFormat

It is used to get the format of the decoded barcode result.

```cpp
virtual BarcodeFormat GetFormat() const = 0;
```

**Return value**

Returns the format of the decoded barcode result.

**See Also**

[Enumeration BarcodeFormat]({{ site.dcv_enumerations }}barcode-reader/barcode-format.html?lang=android)

### GetFormatString

It is used to get the format string of the decoded barcode result.

```cpp
virtual const char* GetFormatString() const = 0;
```

**Return value**

Returns the format string of the decoded barcode result.

### GetText

It is used to get the text result of the decoded barcode.

```cpp
virtual const char* GetText() const = 0;
```

**Return value**

Returns the text result of the decoded barcode.

### GetBytes

It is used to get the text bytes of the decoded barcode result.

```cpp
virtual unsigned char* GetBytes() const = 0;
```

**Return value**

Returns the text bytes of the decoded barcode result.

### GetBytesLength

It is used to get the text bytes length of the decoded barcode result.

```cpp
virtual int GetBytesLength() const = 0;
```

**Return value**

Returns the text bytes length of the decoded barcode result.

### GetLocation

It is used to get the location of the decoded barcode in a quadrilateral.

```cpp
virtual CQuadrilateral GetLocation() const = 0;
```

**Return value**

Returns the location of the decoded barcode in a quadrilateral.

**See Also**

[CQuadrilateral]({{ site.dcv_android_api }}core/basic-structures/quadrilateral.html)

### GetConfidence

It is used to get the confidence of the decoded barcode result.

```cpp
virtual int GetConfidence() const = 0;
```

**Return value**

Returns the confidence of the decoded barcode result.

### GetAngle

It is used to get the angle of the decoded barcode result.

```cpp
virtual int GetAngle() const = 0;
```

**Return value**

Returns the angle of the decoded barcode result.

### GetModuleSize

It is used to get the module size of the decoded barcode result.

```cpp
virtual int GetModuleSize() const = 0;
```

**Return value**

Returns the module size of the decoded barcode result.

### GetDetails

It is used to get the details of the decoded barcode result.

```cpp
virtual const CBarcodeDetails* GetDetails() const = 0;	
```

**Return value**

Returns the details of the decoded barcode result.

**See Also**

- [CAztecDetails]({{ site.android_api }}aztec-details.html)
- [CBarcodeDetails]({{ site.android_api }}barcode-details.html)
- [CDataMatrixDetails]({{ site.android_api }}datamatrix-details.html)
- [COneDCodeDetails]({{ site.android_api }}oned-code-details.html)
- [CPDF417Details]({{ site.android_api }}pdf417-details.html)
- [CQRCodeDetails]({{ site.android_api }}qr-code-details.html)

### IsDPM

It is used to get whether the decoded barcode is a DPM code.

```cpp
virtual bool IsDPM() const = 0;
```

**Return value**

Returns whether the decoded barcode is a DPM code.

### IsMirrored

It is used to get whether the decoded barcode is mirrored.

```cpp
virtual bool IsMirrored() const = 0;
```

**Return value**

Returns whether the decoded barcode is mirrored.

### GetRotationTransformMatrix

It is used to get the rotation transform matrix of the decoded barcode.

```cpp
virtual void GetRotationTransformMatrix(double matrix[9]) const = 0;
```

**Parameters**

`[out] matrix` The rotation transform matrix of the decoded barcode.


