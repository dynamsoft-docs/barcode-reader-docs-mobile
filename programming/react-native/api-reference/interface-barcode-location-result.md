---
layout: default-layout
title: Interface BarcodeLocationResult - Dynamsoft Capture Vision React Native Edition
description: The interface of barcode location result
keywords: Interface BarcodeLocationResult, API reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: BarcodeLocationResult
---

# BarcodeLocationResult

Interface `BarcodeLocationResult`. The location of a quadrilateral area which indicates the location of the detected barcode.

```js
export interface BarcodeLocationResult {
    /**
     * The angle of a barcode. Values range from 0 to 360.
     */
    angle: number;
    /**
     * The coordinates of the quadrilateral points.
     */
    location: Quadrilateral;
}
//# sourceMappingURL=BarcodeLocationResult.d.ts.map
```

- [`Interfaces BarcodeResult`](interface-barcode-result.md)
- [`Interface Quadrilateral`](interface-quadrilateral.md)
- [`Interface Point`](interface-point.md)
