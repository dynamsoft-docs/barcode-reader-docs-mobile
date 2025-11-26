---
layout: default-layout
title: EnumResultStatus - Dynamsoft Barcode Reader Flutter Edition
description: EnumResultStatus of DynamsoftBarcodeReader Flutter is an enumeration class that defines the result status of the BarcodeScanResult.
keywords: BarcodeReader, BarcodeScanResult, EnumResultStatus, BarcodeScanner
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: EnumResultStatus
---

# EnumResultStatus

`EnumResultStatus` is a enumeration that defines the result status of the associated [`BarcodeScanResult`](../capture-vision-router/barcode-result-item.md).

## Definition

*Assembly:* dynamsoft_barcode_reader_bundle_flutter

```dart
enum EnumResultStatus {
    finished,
    canceled,
    exception
}
```

## Members

| Member | Description |
| ------ | ----------- |
| `finished` | The barcode decoding process was a success and the result has been received. |
| `canceled` | The barcode decoding process was cancelled by the user (usually by closing the UI using the close button). |
| `exception` | Something went wrong during the barcode decoding process and an exception has been thrown. |
