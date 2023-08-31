---
layout: default-layout
title: DSBarcodeReaderModule Class - Dynamsoft Barcode Reader Android Edition
description: DSBarcodeReaderModule class defines general functions in the barcode reader module.
keywords: barcode reader module, Android, get version
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSBarcodeReaderModule
permalink: /programming/android/api-reference/barcode-reader-module.html
---

# CBarcodeReaderModule

The `CBarcodeReaderModule` class defines general functions in the barcode reader module.

## Definition

*Namespace:* dynamsoft::dbr

*Assembly:* DynamsoftBarcodeReader

```cpp
class CBarcodeReaderModule 
```

## Methods Summary

| Method                                                    | Description                                        |
| --------------------------------------------------------- | -------------------------------------------------- |
| [GetVersion](#getversion)                                     | Returns the version of the barcode reader module. |

## GetVersion

Returns the version of the barcode reader module.

```cpp
static const char* GetVersion();
```

**Parameters**

None.

**Return Value**

Returns a const char pointer representing the version of the barcode reader module.
