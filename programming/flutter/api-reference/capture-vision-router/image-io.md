---
layout: default-layout
title: ImageIO Class - Dynamsoft Capture Vision Flutter
description: ImageIO class of DCV Flutter provides API to read and write image data to the file system.
keywords: image io, intermediate, capture vision, original image, result, file system, save
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# ImageIO

The `ImageIO` class provides API to handle image input/output operations such as saving images to the file system. This class allows the library to read and write image data to the file system. 

## Definition

*Assembly:* dynamsoft_capture_vision_flutter

```dart
class ImageIO
```

## Methods

### saveToFile

Saves the provided [`ImageData`](image-data.md) object (which represents an image) to a file at the specified file path.

```dart
Future<void> saveToFile(ImageData image, String path, bool overwrite) async
```

**Remarks**

The `overwrite` input parameter should be set to true if the file already exists at the specified file path.

### readFromFile

Reads an image from a file at the specified file path and returns an [`ImageData`](image-data.md) object that represents the image.

```dart
Future<ImageData?> readFromFile(String path) async
```
