---
layout: default-layout
title: Zoom Control for BarcodeScanner - Dynamsoft Barcode Reader Android
description: Learn how to configure zoom control for BarcodeScanner on Android, including auto-zoom and zoom factor.
keywords: BarcodeScanner, scanner, Android, auto-zoom, zoom
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Zoom Control

Zoom control is commonly used when processing small barcodes or scanning from a long distance. There are two zoom control features:

- Auto-zoom: Lets the library determine whether to zoom in.
- Zoom factor: Lets you set the zoom factor directly. This is commonly used when focusing on small barcodes.

## Auto Zoom

Enable auto-zoom so the camera can zoom in automatically.

<div align="center">
    <p><img src="../../../assets/auto-zoom.gif" width="30%" alt="auto-zoom"></p>
    <p>Auto Zoom</p>
</div>


<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
CameraEnhancer mCamera = new CameraEnhancer(this);
try {
   mCamera.enableEnhancedFeatures(EnumEnhancerFeatures.EF_AUTO_ZOOM);
} catch (CameraEnhancerException e) {
   throw new RuntimeException(e);
}
```
2. 
```kotlin
val mCamera = CameraEnhancer(this)
mCamera.enableEnhancedFeatures(EnumEnhancerFeatures.EF_AUTO_ZOOM)
```

**Related API**

- [`enableEnhancedFeatures`]({{ site.dce_android }}primary-api/camera-enhancer.html#enableenhancedfeatures)

## Zoom Factor

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
CameraEnhancer mCamera = new CameraEnhancer(this);
mCamera.setZoomFactor(2.0f);
```
2. 
```kotlin
val mCamera = CameraEnhancer(this)
mCamera.zoomFactor = 2.0f
```

**Related API**

- [`setZoomFactor`]({{ site.dce_android }}primary-api/camera-enhancer.html#setzoomfactor)
