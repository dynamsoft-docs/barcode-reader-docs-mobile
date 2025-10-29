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
enum EnumImagePixelFormat
{
    /** Each pixel is represented by a single bit. **/
    binary,

    /** Each pixel is represented by a single bit and the bits are inverted.  **/
    binaryInverted,

    /** Each pixel is represented by a single byte indicating the intensity of gray. **/
    grayScaled,

    /** A YUV format with a specific arrangement of chroma and luma components. **/
    nv21,

    /** Each pixel is represented by 16 bits: 5 bits for red, 6 bits for green, and 5 bits for blue. **/
    rgb565,

    /** Each pixel is represented by 15 bits: 5 bits each for red, green, and blue. **/
    rgb555,

    /** Each pixel is represented by 24 bits: 8 bits each for red, green, and blue. **/
    rgb888,

    /** Each pixel is represented by 32 bits: 8 bits each for alpha, red, green, and blue. **/
    argb8888,

    /** Each pixel is represented by 48 bits: 16 bits each for red, green, and blue. **/
    rgb161616,

    /** Each pixel is represented by 64 bits: 16 bits each for alpha, red, green, and blue. **/
    argb16161616,

    /** ABGR8888 pixel format, where each pixel is represented by 32 bits: 8 bits each for alpha, blue, green, and red. **/
    abgr8888,

    /** ABGR16161616 pixel format, where each pixel is represented by 64 bits: 16 bits each for alpha, blue, green, and red. **/
    abgr16161616,

    /** Each pixel is represented by 24 bits: 8 bits each for blue, green, and red. **/
    bgr888,

    /** Each pixel is represented by 8 bits in a binary format. **/
    binary8,

    /** NV12 pixel format, a YUV format with a specific arrangement of chroma and luma components. **/
    nv12,

    /** Inverted Binary8 pixel format, where each pixel is represented by 8 bits in a binary format and the bits are inverted. **/
    binary8Inverted,
}
```
