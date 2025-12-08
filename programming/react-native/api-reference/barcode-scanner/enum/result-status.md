---
layout: default-layout
title: EnumResultStatus - Dynamsoft Barcode Reader React Native Edition
description: EnumResultStatus of DynamsoftBarcodeReader React Native is an enumeration class that defines the result status of the BarcodeScanResult.
keywords: BarcodeReader, BarcodeScanResult, EnumResultStatus, BarcodeScanner
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: EnumResultStatus
---

# EnumResultStatus

`EnumResultStatus` is a enumeration that defines the result status of the associated [`BarcodeScanResult`](../capture-vision-router/barcode-result-item.md).

## Definition

*Assembly:* dynamsoft-barcode-reader-bundle-react-native

```tsx
enum EnumResultStatus {
  RS_FINISHED,
  RS_CANCELED,
  RS_EXCEPTION
}
```

## Members

| Member | Description |
| ------ | ----------- |
| `RS_FINISHED` | The barcode decoding process was a success and the result has been received. |
| `RS_CANCELED` | The barcode decoding process was cancelled by the user (usually by closing the UI using the close button). |
| `RS_EXCEPTION` | Something went wrong during the barcode decoding process and an exception has been thrown. |
