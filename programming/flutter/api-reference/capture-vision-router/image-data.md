---
layout: default-layout
title: ImageData Class - Dynamsoft Capture Vision Flutter
description: ImageData class of DCV Flutter represents an image with its raw attributes.
keywords: image data, intermediate, capture vision, original image, result
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# ImageData

The `ImageData` class encapsulates all of an image's data, as well as metadata. It is used to represent an image, and the image's data can then be used for further operations such as analysis, viewing, or saving.

## Definition

*Assembly:* dynamsoft_capture_vision_flutter

```dart
class ImageData
```

## Properties

### bytes

Represents the raw bytes of the image. 

```dart
Uint8List bytes;
```

### width

Represents the width of the image in *pixels*.

```dart
int width;
```

### height

Represents the height of the image in *pixels*.

```dart
int height;
```

### orientation

Represents the orientation of the image as an angle.

```dart
int orientation;
```

### format

Represents the pixel format of the image as a [`EnumImagePixelFormat`](../enum/image-pixel-format.md).

```dart
EnumImagePixelFormat format;
```

**Remarks**

If you would like to change the pixel format of the image, please refer to the method [`setColourChannelUsageType`](camera-enhancer.md#setcolourchannelusagetype) of the `CameraEnhancer` class.

### stride

Represents the number of bytes in a single row of the image.

```dart
int stride;
```