---
layout: default-layout
title: DSOneDCodeDetails Class - Dynamsoft Barcode Reader iOS Edition
description: The DSOneDCodeDetails class represents a barcode in OneD format. It inherits from the DSBarcodeDetails class and contains information about the start & stop char bytes, check digit bytes, and pattern ranges of the barcode.
keywords: DSOneDCodeDetails, api reference, start char bytes, stop char bytes, pattern range, check digit
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSOneDCodeDetails
permalink: /programming/objectivec-swift/api-reference/auxiliary-OneDCodeDetails.html
---

# DSOneDCodeDetails

`OneDCodeDetails` is one of the [`detailedResult`](auxiliary-TextResult.md#detailedresult) in class `TextResult`. It stores the OneD code details.

```java
class com.dynamsoft.dbr.OneDCodeDetails;
```

| Attribute | Type | Descriptions |
|---------- |----- | -------------|
| `moduleSize` | *int* | The barcode module size (the minimum bar width in pixel). |
| `startCharsBytes` | *int* | The start chars in a byte array. |
| `stopCharsBytes` | *int* | The stop chars in a byte array. |
| `checkDigitBytes` | *int* | The check digit chars in a byte array. |
| `startPatternRange` | *int* | The start pattern range of the OneDcode. |
| `middlePatternRange` | *int* | The middle pattern range of the OneDcode. |
| `endPatternRange` | *int* | The end pattern range of the OneDcode. |

## moduleSize

The barcode module size (the minimum bar width in pixel).

```java
int moduleSize
```

## startCharsBytes

The start chars in a byte array.

```java
byte[] startCharsBytes
```

## stopCharsBytes

The stop chars in a byte array.

```java
byte[] stopCharsBytes
```

## checkDigitBytes

The check digit chars in a byte array.

```java
byte[] checkDigitBytes
```

## startPatternRange

The start pattern range of the OneDcode.

```java
byte[] startPatternRange
```

## middlePatternRange

The middle pattern range of the OneDcode.

```java
byte[] middlePatternRange
```

## endPatternRange

The end pattern range of the OneDcode.

```java
byte[] endPatternRange
```
