---
layout: default-layout
title: ImageDrawer Class - Dynamsoft Capture Vision Flutter
description: ImageDrawer class of DCV Flutter provides API to render shapes on images.
keywords: image drawer, intermediate, capture vision, original image, result, draw
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# ImageDrawer

The `ImageDrawer` class provides API to render geometric shapes such as quadrilaterals on images. This class comes in handy when you want to add annotations to an image obtained from a `CapturedResult` or from the `IntermediateResultManager`.

## Definition

*Assembly:* dynamsoft_capture_vision_flutter

```dart
class ImageDrawer
```

## Methods

### drawOnImage

Draws quadrilaterals on the image with the specified style parameters.

```dart
Future<ImageData> drawOnImage(ImageData image, List<Quadrilateral> quadrilaterals, int color, int thickness) async
```

**Remarks**

- `image`: The source image to draw on.
- `quadrilaterals`: List of Quadrilateral objects to render onto the image.
- `color`: ARGB colour value (0xAARRGGBB format)
- `thickness`: The line thickness in pixels.

The method returns an [`ImageData`](image-data.md) object that represents the new image with the rendered shapes.
