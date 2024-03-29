---
layout: default-layout
title: OneDCodeDetails Class - Dynamsoft Barcode Reader Android API Reference
description: This page shows the OneDCodeDetails Class of Dynamsoft Barcode Reader for Android SDK.
keywords: OneDCodeDetails, class, api reference, android
needAutoGenerateSidebar: true
permalink: /programming/android/api-reference/auxiliary-OneDCodeDetails-v7.6.0.html
---

# OneDCodeDetails

Stores the OneD code details.

## Attributes
  
| Attribute | Type |
|---------- | ---- |
| [`moduleSize`](#modulesize) | *int* |
| [`startCharsBytes`](#startcharsbytes) | *byte\[\]* |
| [`stopCharsBytes`](#stopcharsbytes) | *byte\[\]* |
| [`checkDigitBytes`](#checkdigitbytes) | *byte\[\]* |

### moduleSize

The barcode module size (the minimum bar width in pixel).

```java
int com.dynamsoft.barcode.LocalizationResult.moduleSize
```

### startCharsBytes

The start chars in a byte array.

```java
byte[] com.dynamsoft.barcode.LocalizationResult.startCharsBytes
```

### stopCharsBytes

The stop chars in a byte array.

```java
byte[] com.dynamsoft.barcode.LocalizationResult.stopCharsBytes
```

### checkDigitBytes

The check digit chars in a byte array.

```java
byte[] com.dynamsoft.barcode.LocalizationResult.checkDigitBytes
```
