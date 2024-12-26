---
layout: default-layout
title: EnumResultStatus - Dynamsoft Barcode Scanner Android Edition
description: EnumResultStatus of DynamsoftBarcodeScanner Android is an enumeration class that defines the result status of the BarcodeScanResult.
keywords: scanner, activity, startCapturing, license 
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: EnumResultStatus
---

# EnumResultStatus

`EnumResultStatus` is a enumeration class that defines the result status of the `BarcodeScanResult`.

## Definition

*Assembly:* DynamsoftBarcodeReaderBundle.aar

*Namespace:* com.dynamsoft.dbrbundle.ui

```java
@IntDef(value = {RS_FINISHED, RS_CANCELED, RS_EXCEPTION})
public @interface EnumResultStatus {
    int RS_FINISHED = 0;
    int RS_CANCELED = 1;
    int RS_EXCEPTION = 2;
}
```
