---
layout: default-layout
title: EnumBarcodeColourMode of Dynamsoft Capture Vision Flutter Edition
description: The enumeration of mode parameter barcodeColourmodes
keywords: EnumBarcodeColourMode, API Reference, Flutter
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: EnumBarcodeColourMode
---

# EnumBarcodeColourMode

> *Added in version 1.2.0.*

`EnumBarcodeColourMode` is the enumeration for user to configure **mode parameter** `barcodeColourModes` via class [`DBRRuntimeSettings`](class-dbr-runtime-settings.md).

```dart
class EnumBarcodeColourMode {
  static const int BICM_SKIP = 0;
  static const int BICM_DARK_ON_LIGHT = 1;
  static const int BICM_LIGHT_ON_DARK = 2;
  static const int BICM_DARK_ON_DARK = 4;
  static const int BICM_LIGHT_ON_LIGHT = 8;
  static const int BICM_DARK_LIGHT_MIXED = 16;
  static const int BICM_DARK_ON_LIGHT_DARK_SURROUNDING = 32;
}
```
