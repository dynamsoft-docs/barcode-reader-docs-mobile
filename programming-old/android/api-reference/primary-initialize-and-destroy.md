---
layout: default-layout
title: BarcodeReader initialization - Dynamsoft Barcode Reader Android API Reference
description: This page shows BarcodeReader initialization methods of Dynamsoft Barcode Reader for Android SDK.
keywords: BarcodeReader, initialization, api reference, android
needAutoGenerateSidebar: true
noTitleIndex: true
permalink: /programming/android/api-reference/primary-initialize-and-destroy.html
---

# initialization methods

  | Method               | Description |
  |----------------------|-------------|
  | [`BarcodeReader`](#barcodereader-initialization) | Initialization of `BarcodeReader` object.|

---

## BarcodeReader Initialization

Initialization of `BarcodeReader` object without a license.

```java
BarcodeReader() throws BarcodeReaderException
```

**Exceptions**

A [`BarcodeReaderException`](auxiliary-BarcodeReaderException.html) is thrown when a null pointer is returned.

**Code Snippet**

```java
BarcodeReader reader;
reader = new BarcodeReader();
```

**Remarks**

`BarcodeReader(String license)` is deprecated and will be removed in the future. Please use `BarcodeReader()` instead.
