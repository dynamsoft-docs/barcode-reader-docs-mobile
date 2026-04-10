---
layout: default-layout
title: ECISegment Class - Dynamsoft Barcode Reader MAUI Edition
description: ECISegment class of Dynamsoft Barcode Reader MAUI represents the Extended Channel Interpretation (ECI) information within a barcode, specifying the character encoding used for a portion of the decoded bytes.
keywords: ECISegment, ECI, character encoding, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: ECISegment
---

# ECISegment Class

`ECISegment` is a class that represents the Extended Channel Interpretation (ECI) information within a barcode. Each ECI segment specifies the character encoding used for a portion of the decoded bytes. The charset names follow the IANA character set registry (e.g. "UTF-8", "ISO-8859-1").

## Definition

*Namespace:* Dynamsoft.BarcodeReader.Maui

*Assembly:* Dynamsoft.BarcodeReader.Maui

```csharp
class ECISegment
```

## Properties

| Properties | Type | Description |
| ---------- | ---- | ------------|
| [`EciValue`](#ecivalue) | *int* | The ECI assignment number as defined by ISO/IEC 15424. |
| [`CharsetEncoding`](#charsetencoding) | *string* | The charset encoding name defined by IANA (e.g. "UTF-8", "ISO-8859-1"). |
| [`StartIndex`](#startindex) | *int* | The start index of this ECI segment in the decoded barcode bytes. |
| [`Length`](#length) | *int* | The length (in bytes) of this segment within the decoded barcode bytes. |

### EciValue

The ECI assignment number as defined by ISO/IEC 15424. This value identifies the character set encoding used in this segment.

```csharp
int EciValue { get; }
```

### CharsetEncoding

The charset encoding name defined by IANA (e.g. "UTF-8", "ISO-8859-1"). This specifies the character encoding scheme used to interpret the bytes in this segment.

```csharp
string CharsetEncoding { get; }
```

### StartIndex

The start index of this ECI segment in the decoded barcode bytes. This indicates the position where this segment begins within the overall decoded byte sequence.

```csharp
int StartIndex { get; }
```

### Length

The length (in bytes) of this segment within the decoded barcode bytes. This specifies how many bytes in the decoded data belong to this ECI segment.

```csharp
int Length { get; }
```
