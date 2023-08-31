---
layout: default-layout
title: DSBarcodeDetails Class - Dynamsoft Barcode Reader iOS Edition
description: DSBarcodeDetails class represents the details of a barcode. It is an abstract base class.
keywords: BarcodeDetails, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSBarcodeResultItem
permalink: /programming/objectivec-swift/api-reference/barcode-details.html
---

# DSBarcodeDetails

The `DSBarcodeDetails` class represents the details of a barcode. It is an abstract base class.

## Definition

*Namespace:* dynamsoft::dbr

*Assembly:* DynamsoftBarcodeReader

```cpp
class DSBarcodeDetails
```

## Methods

| Method               | Description |
|----------------------|-------------|
| [`~DSBarcodeDetails`](#cbarcodedetails) | Destructor. |

### ~DSBarcodeDetails

Destructor.

```cpp
virtual ~DSBarcodeDetails(){};
```

**Remarks**

This is a pure virtual destructor. This means that this class cannot be instantiated on its own, but must be subclassed.
