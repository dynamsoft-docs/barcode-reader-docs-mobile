---
layout: default-layout
title: DecodedBarcodeElement Class - Dynamsoft Barcode Reader Android Edition
description: DecodedBarcodeElement class represents a decoded barcode element. It inherits from the RegionObjectElement class and provides additional functionality for retrieving information about the decoded barcode.
keywords: text, bytes, DecodedBarcodeElement, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DecodedBarcodeElement
permalink: /programming/android/api-reference/decoded-barcode-element.html
---

# DecodedBarcodeElement Class

The `DecodedBarcodeElement` class represents a decoded barcode element. It inherits from the `CRegionObjectElement` class and provides additional functionality for retrieving information about the decoded barcode.

## Definition

*Namespace:* dynamsoft::dbr

*Assembly:* DynamsoftBarcodeReader

*Inheritance:* [CRegionObjectElement]({{ site.dcv_android_api }}core/intermediate-results/region-object-element.html) -> DecodedBarcodeElement

```cpp
class DecodedBarcodeElement : public CRegionObjectElement
```

## Methods

| Method | Description |
| --- | --- |
| [`~DecodedBarcodeElement`](#cdecodedbarcodeelement) | Destructor. |
| [`GetFormat`](#getformat) | Gets the format of the barcode. |
| [`GetFormatString`](#getformatstring) | Gets the string representation of the barcode format. |
| [`GetText`](#gettext) | Gets the text of the decoded barcode. |
| [`GetBytes`](#getbytes)| Gets the raw bytes of the decoded barcode.|
| [`GetBytesLength`](#getbyteslength)  | Gets the length of the raw bytes of the decoded barcode.|
| [`GetDetails`](#getdetails) | Gets the details of the decoded barcode.|
| [`IsDPM`](#isdpm)| Determines whether the decoded barcode is a DPM (Direct Part Marking) code.|
| [`IsMirrored`](#ismirrored)| Determines whether the decoded barcode is mirrored.|
| [`GetAngle`](#getangle) | Gets the orientation angle of the barcode. |
| [`GetModuleSize`](#getmodulesize) | Gets the module size of the barcode. |
| [`GetConfidence`](#getconfidence) | Gets the confidence score of the barcode recognition result. |
| [`GetExtendedBarcodeResultsCount`](#getextendedbarcoderesultscount) | Gets the number of extended barcode results for the decoded barcode.|
| [`GetExtendedBarcodeResult`](#getextendedbarcoderesult) | Gets the extended barcode result at the specified index for the decoded barcode.|

### ~DecodedBarcodeElement

Destructor.

```cpp
virtual ~DecodedBarcodeElement() {}
```

### GetFormat

It is used to get the format of the barcode.

```cpp
BarcodeFormat GetFormat()
```

**Return value**

Returns the format of the barcode.

**See Also**

[Enumeration BarcodeFormat]({{ site.dcv_enumerations }}barcode-reader/barcode-format.html?lang=android)

### GetFormatString

It is used to get the string representation of the barcode format.

```cpp
const char* GetFormatString() const
```

**Return value**

Returns the string representation of the barcode format.

### GetText

Gets the text of the decoded barcode.

```cpp
virtual const char* GetText() const = 0;
```

**Return value**

Returns a pointer to the text of the decoded barcode.

### GetBytes

Gets the raw bytes of the decoded barcode.

```cpp
virtual unsigned char* GetBytes() const = 0;
```

**Return value**

Returns a pointer to the raw bytes of the decoded barcode.

### GetBytesLength

Gets the length of the raw bytes of the decoded barcode.

```cpp
virtual int GetBytesLength() const = 0;
```

**Return value**

Returns the length of the raw bytes of the decoded barcode.

### GetDetails

Gets the details of the decoded barcode.

```cpp
virtual const CBarcodeDetails* GetDetails() const = 0;
```

**Return value**

Returns a pointer to the details of the decoded barcode.

**See Also**

- [CAztecDetails]({{ site.android_api }}aztec-details.html)
- [CBarcodeDetails]({{ site.android_api }}barcode-details.html)
- [CDataMatrixDetails]({{ site.android_api }}datamatrix-details.html)
- [COneDCodeDetails]({{ site.android_api }}oned-code-details.html)
- [CPDF417Details]({{ site.android_api }}pdf417-details.html)
- [CQRCodeDetails]({{ site.android_api }}qr-code-details.html)

### IsDPM

Determines whether the decoded barcode is a DPM (Direct Part Marking) code.

```cpp
virtual bool IsDPM() const = 0;
```

**Return value**

Returns true if the decoded barcode is a DPM code, false otherwise.

### IsMirrored

Determines whether the decoded barcode is mirrored.

```cpp
virtual bool IsMirrored() const = 0;
```

**Return value**

Returns true if the decoded barcode is mirrored, false otherwise.

### GetAngle

It is used to get the orientation angle of the barcode.

```cpp
int GetAngle() const
```

**Return value**

Returns the orientation angle of the barcode.

### GetModuleSize

It is used to get the module size of the barcode.

```cpp
int GetModuleSize() const
```

**Return value**

Returns the module size of the barcode.

### GetConfidence

It is used to get the confidence score of the barcode recognition result.

```cpp
int GetConfidence() const
```

**Return value**

Returns the confidence score of the barcode recognition result.

### GetExtendedBarcodeResultsCount

Gets the number of extended barcode results for the decoded barcode.

```cpp
virtual int GetExtendedBarcodeResultsCount() const = 0;
```

**Return value**

Returns the number of extended barcode results for the decoded barcode.

### GetExtendedBarcodeResult

Gets the extended barcode result at the specified index for the decoded barcode.

```cpp
virtual const CExtendedBarcodeResult* GetExtendedBarcodeResult(int index) const = 0;
```

**Parameters**

`[in] index` The index of the extended barcode result to retrieve.

**Return value**

Returns a pointer to the extended barcode result at the specified index for the decoded barcode.

**See Also**

[CExtendedBarcodeResult]({{ site.android_api }}extended-barcode-result.html)
