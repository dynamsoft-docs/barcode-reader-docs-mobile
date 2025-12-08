---
layout: default-layout
title: EnumScanningMode - Dynamsoft Barcode Reader React Native Edition
description: EnumScanningMode of DynamsoftBarcodeReader React Native is an enumeration class that defines the scanning mode.
keywords: BarcodeScanner, ScanningMode, flutter, barcode reader, mode
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: EnumScanningMode
---

# EnumScanningMode

`EnumScanningMode` is a enumeration class that determines the scanning mode that the `BarcodeScanner` instance will operate in.

## Definition

*Assembly:* dynamsoft-barcode-reader-bundle-react-native

```tsx
enum EnumScanningMode {
  SM_SINGLE,
  SM_MULTIPLE
}
```

## Members

| Member | Description |
| ------ | ----------- |
| `SM_SINGLE` | Used for scanning a single barcode at a time, prioritizing speed over read rate. |
| `SM_MULTIPLE` | Used for scanning multiple barcodes at a time, finding a balance between speed and read rate. |
