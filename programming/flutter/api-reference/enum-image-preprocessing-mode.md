---
layout: default-layout
title: EnumImagePreprocessingMode of Dynamsoft Capture Vision Flutter Edition
description: The enumeration of mode parameter imagePreprocessingmodes
keywords: EnumImagePreprocessingMode, API Reference, Flutter
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: EnumImagePreprocessingMode
---

# EnumImagePreprocessingMode

> *Added in version 1.2.0.*

`EnumImagePreprocessingMode` is the enumeration for user to configure **mode parameter** `imagePreprocessingModes` via class [`DBRRuntimeSettings`](class-dbr-runtime-settings.md).

```dart
class EnumImagePreprocessingMode {
  static const int IPM_SKIP = 0;
  static const int IPM_AUTO = 1;
  static const int IPM_GENERAL = 2;
  static const int IPM_GRAY_EQUALIZE = 4;
  static const int IPM_GRAY_SMOOTH = 8;
  static const int IPM_SHARPEN_SMOOTH = 16;
  static const int IPM_MORPHOLOGY = 32;
}
```
