---
layout: default-layout
title: EnumFilterType - Dynamsoft Barcode Reader Flutter
description: Enumeration EnumFilterType of DBR Flutter Edition defines the types of filters that can be applied to an image.
keywords: filter type, capture vision, image, processor
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: EnumFilterType
---

# EnumFilterType

`EnumFilterType` is an enumeration that specifies the different types of filters that can be applied to an image for further processing.

## Definition

*Assembly:* dynamsoft_capture_vision_flutter

```dart
enum EnumFilterType {
    highPass,
    sharpen,
    smooth
}
```

## Members

| Member | Description |
| ------ | ----------- |
| `highPass` | Enhances the edges and fine details by attenuating low-frequency components. |
| `sharpen` | Increases contrast along edges to make the image appear more defined. |
| `smooth` | Reduces noise and detail by averaging pixel values, creating a softening effect. |
