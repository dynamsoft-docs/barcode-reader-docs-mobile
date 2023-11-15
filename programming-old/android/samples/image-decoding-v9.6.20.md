---
layout: default-layout
title: Image Decoding Sample - Dynamsoft Barcode Reader for Android
description: This is the page of ImageDecoding sample of Dynamsoft Barcode Reader for Android SDK.
keywords: android, samples, Image Decoding
needAutoGenerateSidebar: true
breadcrumbText: ImageDecoding
permalink: /programming/android/samples/image-decoding-v9.6.20.html
---

# ImageDecoding Sample

`ImageDecoding` sample shows how to pick an image from system album and decode the image.

View the sample:

- <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/v9.6.20/android/Java/ImageDecoding/" target="_blank">Java (Android) ImageDecoding Sample (v9.6.20)</a>

Generally, you can use the following methods to decode an image file:

- [`decodeFile`](../api-reference/primary-decode.html#decodefile): Decode an image file with a file path.
- [`decodeFileInMemory`](../api-reference/primary-decode.html#decodefileinmemoryfilebytes): Decode an image file in memory with a byte buffer or fileStream.
- [`decodeBase64String`](../api-reference/primary-decode.html#decodebase64string): Decode an image file in memory with a Base64 string.
- [`decodeBufferedImage`](../api-reference/primary-decode.html#decodebufferedimage): Decode `Bitmap`.

Different from processing the video streaming, the read rate performance is much more important when processing a single image. It is suggested to switch to the `PresetTemplate` to `IMAGE_READ_RATE` to improve the read rate performance.

In `ImageDecoding` sample, the image file picked from album is firstly read in the memory and displayed on the view. As a result, it is processed by method `decodeFileInMemory`. You can also use a similar way to get the file path of the image file and process it with `decodeFile`. You can get full code of how to extract the file path from another sample: <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/android/Java/PerformanceSettings" target="_blank">PerformanceSettings</a>.
