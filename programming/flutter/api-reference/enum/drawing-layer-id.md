---
layout: default-layout
title: EnumDrawingLayerId - Dynamsoft Barcode Reader Flutter
description: Enumeration EnumDrawingLayerId of DBR Flutter Edition defines the different drawing layers that the CameraView provides.
keywords: drawing layer, Flutter, camera enhancer, UI
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: EnumDrawingLayerId
---

# EnumDrawingLayerId

`EnumDrawingLayerId` is an enumeration that defines the different drawing layers that the CameraView provides. The drawing layer is responsible for creating the highlight boxes around detected barcodes and other captured results. By default, there is a drawing layer assigned to each functional product under Capture Vision. 

## Definition

*Assembly:* dynamsoft_capture_vision_flutter

```dart
enum EnumDrawingLayerId {
    ddn,
    dbr,
    dlr,
    tip
}
```

## Members

| Member | Description |
| ------ | ----------- |
| `ddn` | The preset DrawingLayer for the Dynamsoft Document Normalizer. |
| `dbr` | The preset DrawingLayer for the Dynamsoft Barcode Reader. |
| `dlr` | The preset DrawingLayer for the Dynamsoft Label Recognizer. |
| `tip` | A custom DrawingLayer for tips. |
