---
layout: default-layout
title: Dynamsoft Barcode Reader Android API Reference - ImageData Class
description: This page shows the ImageData Class of Dynamsoft Barcode Reader for Android SDK.
keywords: ImageData, class, api reference, android
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
permalink: /programming/android/api-reference/auxiliary-ImageData.html
---


# ImageData

Stores the image data.  

```java
class com.dynamsoft.dbr.ImageData
```

| Method | Description |
| ------ | ----------- |
| [`toBitmap`](#tobitmap) | Convert the `ImageData` to a `Bitmap`. |

## tobitmap

Convert the `ImageData` to a `Bitmap`.

```java
Bitmap toBitmap() throws BarcodeReaderException
```

**Return Value**

A Bitmap that converted from the `ImageData`.

**Code Snippet**

```java
Bitmap bitmap = imageData.toBitmap();
```

| Attribute | Type | Descriptions |
|---------- | ---- | ------------ |
| [`bytes`](#bytes) | *byte\[\]* | The image data content in a byte array. |
| [`width`](#width) | *int* | The width of the image in pixels. |
| [`height`](#height) | *int* | The height of the image in pixels. |
| [`stride`](#stride) | *int* | The stride (or scan width) of the image. |
| [`format`](#format) | *int* | The image pixel format used in the image byte array. |
| [`orientation`](#orientation) | *int* | The orientation of the image. |

## bytes

The image data content in a byte array.

```java
byte[] bytes
```

## width

The width of the image in pixels.

```java
int width
```

## height

The height of the image in pixels.

```java
int height
```

## stride

The stride (or scan width) of the image.

```java
int stride
```

## format

The image pixel format used in the image byte array.

```java
int format
```

## orientation

The orientation of the image. It can be 0, 90, 180, or 270 based on the device orientation.

```java
int orientation
```
