---
layout: default-layout
title: EnumScanningMode - Dynamsoft Barcode Reader Android Edition
description: EnumScanningMode of Dynamsoft Barcode Reader Android is an enumeration class that defines the scanning mode.
keywords: scan modes, scanning modes, single, multiple barcodes
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: EnumScanningMode
---

# EnumScanningMode

`EnumScanningMode` is an enumeration class that defines the scanning mode. Currently, it is use for switching between single-barcode and multi-barcode scanning modes.

## Definition

*Assembly:* DynamsoftBarcodeReaderBundle.aar

*Namespace:* com.dynamsoft.dbrbundle.ui

```java
@IntDef(value = {SM_SINGLE, SM_MULTIPLE})
public @interface EnumScanningMode {
    // The scan mode for scanning single barcode.
    int SM_SINGLE = 0;
    // The scan mode for scanning multiple barcodes.
    int SM_MULTIPLE = 1;
}
```
