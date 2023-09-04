---
layout: default-layout
title: BarcodeDetails Class - Dynamsoft Barcode Reader Android Edition
description: BarcodeDetails class represents the details of a barcode. It is an abstract base class.
keywords: BarcodeDetails, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: BarcodeResultItem
permalink: /programming/android/api-reference/barcode-details.html
---

# BarcodeDetails

The `BarcodeDetails` class represents the details of a barcode. It is an abstract base class.

## Definition

*Namespace:* dynamsoft::dbr

*Assembly:* DynamsoftBarcodeReader

```cpp
class BarcodeDetails
```

## Methods

| Method               | Description |
|----------------------|-------------|
| [`~BarcodeDetails`](#cbarcodedetails) | Destructor. |

### ~BarcodeDetails

Destructor.

```cpp
virtual ~BarcodeDetails(){};
```

**Remarks**

This is a pure virtual destructor. This means that this class cannot be instantiated on its own, but must be subclassed.
