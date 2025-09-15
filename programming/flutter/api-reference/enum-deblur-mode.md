---
layout: default-layout
title: EnumDeblurMode of Dynamsoft Capture Vision Flutter Edition
description: The enumeration of mode parameter deblurModes
keywords: EnumDeblurMode, API Reference, Flutter
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: EnumDeblurMode
---

# EnumDeblurMode

> *Added in version 1.2.0.*

`EnumDeblurMode` is the enumeration for user to configure **mode parameter** `deblurModes` via class [`DBRRuntimeSettings`](class-dbr-runtime-settings.md).

```dart
class EnumDeblurMode {
  static const int DM_SKIP = 0;
  static const int DM_DIRECT_BINARIZATION = 1;
  static const int DM_THRESHOLD_BINARIZATION = 2;
  static const int DM_GRAYE_EQULIZATION = 4;
  static const int DM_SMOOTHING = 8;
  static const int DM_MORPHING = 16;
  static const int DM_DEEP_ANALYSIS = 32;
  static const int DM_SHARPENING = 64;
  static const int DM_BASED_ON_LOC_BIN = 128;
  static const int DM_SHARPENING_SMOOTHING = 256;
}
```
