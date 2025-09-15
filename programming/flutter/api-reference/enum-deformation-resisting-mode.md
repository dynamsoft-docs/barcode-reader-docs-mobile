---
layout: default-layout
title: EnumDeformationResistingMode of Dynamsoft Capture Vision Flutter Edition
description: The enumeration of mode parameter deformationResistingmodes
keywords: EnumDeformationResistingMode, API Reference, Flutter
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: EnumDeformationResistingMode
---

# EnumDeformationResistingMode

> *Added in version 1.2.0.*

`EnumDeformationResistingMode` is the enumeration for user to configure **mode parameter** `deformationResistingModes` via class [`DBRRuntimeSettings`](class-dbr-runtime-settings.md).

```dart
class EnumDeformationResistingMode {
  static const int DRM_SKIP = 0;
  static const int DRM_AUTO = 1;
  static const int DRM_GENERAL = 2;
  static const int DRM_BROAD_WARP = 4;
  static const int DRM_LOCAL_REFERENCE = 8;
  static const int DRM_DEWRINKLE = 16;
}
```
