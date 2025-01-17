---
layout: default-layout
title: EnumResultStatus - Dynamsoft Barcode Reader Android Edition
description: EnumResultStatus of Dynamsoft Barcode Reader Android is an enumeration class that defines the result status of the BarcodeScanResult.
keywords: scanner, activity, startCapturing, license 
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: EnumResultStatus
---

# EnumResultStatus

`EnumResultStatus` is an enumeration class that defines the result status of the `BarcodeScanResult`.

If the status is **finished**, that indicates that the result has been decoded and is available - while **canceled** indicates that the operation has been halted. If the result status is **exception**, then that means that an error has occurred during the barcode detection process.


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
