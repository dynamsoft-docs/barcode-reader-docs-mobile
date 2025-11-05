---
layout: default-layout
title: ImageProcessor Class - Dynamsoft Capture Vision Flutter
description: ImageProcessor class of DCV Flutter provides API to crop images based on specified regions.
keywords: image processor, intermediate, capture vision, original image, crop
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# ImageProcessor

The `ImageProcessor` class provides API to crop images based on specified regions.

## Definition

*Assembly:* dynamsoft_capture_vision_flutter

```dart
class ImageProcessor
```

## Methods

### cropImage

Crops the image (as an [`ImageData`](image-data.md) object) to the region defined by the rectangle.

```dart
Future<ImageData?> cropImage(ImageData image, DSRect rect) async
```

**Remarks**

The method returns an [`ImageData`](image-data.md) object that represents the newly cropped image. The method returns `null` if the cropping fails (invalid rectangle, out of bounds, a null `ImageData` object, etc.).

### cropAndDeskewImage

Crops the image (as an [`ImageData`](image-data.md) object) to the region defined by the Quadrilateral.

```dart
Future<ImageData?> cropAndDeskewImage(ImageData image, Quadrilateral quadrilateral, {
    int dstWidth = 0,
    int dstHeight = 0,
    int padding = 0,
  }) async
```

**Remarks**

The `quadrilateral` input parameter defines the region to extract as four corner points. The method returns an [`ImageData`](image-data.md) object that represents the newly cropped image. The method returns `null` if the cropping fails (invalid Quadrilateral, out of bounds, a null `ImageData` object, etc.).

### adjustBrightness

Adjusts the brightness of the image (as an [`ImageData`](image-data.md) object) based on the specified brightness value.

```dart
Future<ImageData?> adjustBrightness(ImageData image, int brightness) async
```

**Remarks**

The `brightness` input parameter ranges from -100 to 100. Positive values increase brightness while negative values decrease it. The method returns `null` if the adjustment fails.

### adjustContrast

Adjusts the contrast of the image (as an [`ImageData`](image-data.md) object) based on the specified contrast value.

```dart
Future<ImageData?> adjustContrast(ImageData image, int contrast) async
```

**Remarks**

The `contrast` input parameter ranges from -100 to 100. Positive values increase brightness while negative values decrease it. The method returns `null` if the adjustment fails.

### filterImage

Applies a filter (represented with [`EnumFilterType`](../enum/filter-type.md)) to the image (as an [`ImageData`](image-data.md) object).

```dart
Future<ImageData?> filterImage(ImageData image, EnumFilterType type) async
```

**Remarks**

The method returns `null` if the filtering fails.

### convertToGray

Converts the image (as an [`ImageData`](image-data.md) object) to grayscale using specified channel weights.

```dart
Future<ImageData?> convertToGray(ImageData image, {
  double r = 0.3,
  double g = 0.59,
  double b = 0.11,
}) async
```

**Remarks**

- `r`: Weight of the red channel (default value is 0.3).
- `g`: Weight of the green channel (default value is 0.59).
- `b`: Weight of the blue channel (default value is 0.11).

The method returns `null` if the conversion fails.

### convertToBinaryGlobal

Converts the image (as an [`ImageData`](image-data.md) object) to a binary (black and white) format using global thresholding.

```dart
Future<ImageData?> convertToBinaryGlobal(ImageData image, {
  int threshold = -1,
  bool inverse = false,
}) async
```

Remarks

- `threshold`: A value that ranges between 0 and 255. If -1, Otsu's method is used to determine the optimal threshold.
- `inverse`: If `true`, inverts the binary colours, resulting in a negative filter on the image.

### convertToBinaryLocal

Converts the image (as an [`ImageData`](image-data.md) object) to a binary (black and white) format using local adaptive thresholding.

```dart
Future<ImageData?> convertToBinaryLocal(
  ImageData image, {
  int blockSize = 0,
  int compensation = 0,
  bool inverse = false,
}) async
```

**Remarks**

- `blockSize`: Size of the local region (must be odd and >= 3).
- `compensation`: Value to adjust the threshold (typically 0-10).
- `inverse`: If `true`, inverts the binary colours, resulting in a negative filter on the image.
