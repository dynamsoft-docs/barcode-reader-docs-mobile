---
layout: default-layout
title: ECISegment Class - Dynamsoft Barcode Reader Android Edition
description: ECISegment class of Dynamsoft Barcode Reader Android represents the Extended Channel Interpretation (ECI) information within a barcode, specifying the character encoding used for a portion of the decoded bytes.
keywords: ECISegment, ECI, character encoding, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: ECISegment
---

# ECISegment Class

`ECISegment` is a class that represents the Extended Channel Interpretation (ECI) information within a barcode. Each ECI segment specifies the character encoding used for a portion of the decoded bytes. The charset names follow the IANA character set registry (e.g. "UTF-8", "ISO-8859-1").

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.aar

*Namespace:* com.dynamsoft.dbr

```java
class ECISegment
```

## Attributes

| Attribute | Description |
| --------- | ------------|
| [`eciValue`](#ecivalue) | The ECI assignment number as defined by ISO/IEC 15424. |
| [`charsetEncoding`](#charsetencoding) | The charset encoding name defined by IANA (e.g. "UTF-8", "ISO-8859-1"). |
| [`startIndex`](#startindex) | The start index of this ECI segment in the decoded barcode bytes. |
| [`length`](#length) | The length (in bytes) of this segment within the decoded barcode bytes. |

### eciValue

The ECI assignment number as defined by ISO/IEC 15424. This value identifies the character set encoding used in this segment.

```java
int eciValue;
```

### charsetEncoding

The charset encoding name defined by IANA (e.g. "UTF-8", "ISO-8859-1"). This specifies the character encoding scheme used to interpret the bytes in this segment.

```java
String charsetEncoding;
```

### startIndex

The start index of this ECI segment in the decoded barcode bytes. This indicates the position where this segment begins within the overall decoded byte sequence.

```java
int startIndex;
```

### length

The length (in bytes) of this segment within the decoded barcode bytes. This specifies how many bytes in the decoded data belong to this ECI segment.

```java
int length;
```