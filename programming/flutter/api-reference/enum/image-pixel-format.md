---
layout: default-layout
title: EnumImagePixelFormat - Dynamsoft Barcode Reader Flutter
description: Enumeration EnumImagePixelFormat of DBR Flutter Edition defines the available colour channels for the Camera Enhancer to use when capturing images or frames
keywords: colour channel, capture vision, camera, enhancer, pixel, format
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: EnumImagePixelFormat
---

# EnumImagePixelFormat

`EnumImagePixelFormat` is an enumeration that specifies the different pixel formats of an image. From this enumeration, you can determine if an image is binary, grayscale, or colour. 

## Definition

*Assembly:* dynamsoft_capture_vision_flutter

```dart
enum EnumImagePixelFormat {
    binary,
    binaryInverted,
    grayScaled,
    nv21,
    rgb565,
    rgb555,
    rgb888,
    argb8888,
    rgb161616,
    argb16161616,
    abgr8888,
    abgr16161616,
    bgr888,
    binary8,
    nv12,
    binary8Inverted
}
```

## Members

| Member | Description |
| ------ | ----------- |
| `binary` | Each pixel is represented by a single bit. |
| `binaryInverted` | Each pixel is represented by a single bit and the bits are inverted. |
| `grayScaled` | Each pixel is represented by a single byte indicating the intensity of gray. |
| `nv21` | A YUV format with a specific arrangement of chroma and luma components. |
| `rgb565` | Each pixel is represented by 16 bits: 5 bits for red, 6 bits for green, and 5 bits for blue. |
| `rgb555` | Each pixel is represented by 15 bits: 5 bits each for red, green, and blue. |
| `rgb888` | Each pixel is represented by 24 bits: 8 bits each for red, green, and blue. |
| `argb8888` | Each pixel is represented by 32 bits: 8 bits each for alpha, red, green, and blue. |
| `rgb161616` | Each pixel is represented by 48 bits: 16 bits each for red, green, and blue. |
| `argb16161616` | Each pixel is represented by 64 bits: 16 bits each for alpha, red, green, and blue. |
| `abgr8888` | ABGR8888 pixel format, where each pixel is represented by 32 bits: 8 bits each for alpha, blue, green, and red. |
| `abgr16161616` | ABGR16161616 pixel format, where each pixel is represented by 64 bits: 16 bits each for alpha, blue, green, and red. |
| `bgr888` | Each pixel is represented by 24 bits: 8 bits each for blue, green, and red. |
| `binary8` | Each pixel is represented by 8 bits in a binary format. |
| `nv12` | NV12 pixel format, a YUV format with a specific arrangement of chroma and luma components. |
| `binary8Inverted` | Inverted Binary8 pixel format, where each pixel is represented by 8 bits in a binary format and the bits are inverted. |
