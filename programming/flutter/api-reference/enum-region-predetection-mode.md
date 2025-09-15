---
layout: default-layout
title: EnumRegionPredetectionMode of Dynamsoft Capture Vision Flutter Edition
description: The enumeration of mode parameter regionPredetectionmodes
keywords: EnumRegionPredetectionMode, API Reference, Flutter
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: EnumRegionPredetectionMode
---

# EnumRegionPredetectionMode

> *Added in version 1.2.0.*

`EnumRegionPredetectionMode` is the enumeration for user to configure **mode parameter** `regionPredetectionModes` via class [`DBRRuntimeSettings`](class-dbr-runtime-settings.md).

```dart
class EnumRegionPredetectionMode {
  static const int RPM_SKIP = 0;
  static const int RPM_AUTO = 1;
  static const int RPM_GENERAL = 2;
  static const int RPM_GENERAL_RGB_CONTRAST = 4;
  static const int RPM_GENERAL_GRAY_CONTRAST = 8;
  static const int RPM_GENERAL_HSV_CONTRAST = 16;
}
```
