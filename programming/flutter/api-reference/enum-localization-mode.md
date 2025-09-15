---
layout: default-layout
title: EnumLocalizationMode of Dynamsoft Capture Vision Flutter Edition
description: The enumeration of mode parameter localizationModes
keywords: EnumLocalizationMode, API Reference, Flutter
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: EnumLocalizationMode
---

# EnumLocalizationMode

> *Added in version 1.2.0.*

`EnumLocalizationMode` is the enumeration for user to configure **mode parameter** `localizationModes` via class [`DBRRuntimeSettings`](class-dbr-runtime-settings.md).

```dart
class EnumLocalizationMode {
  static const int LM_SKIP = 0;
  static const int LM_AUTO = 1;
  static const int LM_CONNECTED_BLOCKS = 2;
  static const int LM_STATISTICS = 4;
  static const int LM_LINES = 8;
  static const int LM_SCAN_DIRECTLY = 16;
  static const int LM_STATISTICS_MARKS = 32;
  static const int LM_STATISTICS_POSTAL_CODE = 64;
  static const int LM_CENTRE = 128;
  static const int LM_ONED_FAST_SCAN = 256;
}
```
