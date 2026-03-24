---
layout: default-layout
title: Read from camera - Dynamsoft Barcode Reader Android
description: Learn how to read barcodes from the camera using the Dynamsoft Barcode Reader Android SDK.
keywords: user guide, read from camera, Android, java, kotlin
noTitleIndex: true
needGenerateH3Content: true
needAutoGenerateSidebar: true
---

# Read from camera

> [!Important]
> This page is for **Foundational APIs** only. Refer to [Quick Start](../../user-guide.md) for how to scan from camera with `BarcodeScanner` component.

Follow these three steps to read barcodes from the camera:

1. Set input
2. Register result receiver
3. Start capturing

## Set input

### CameraEnhancer - Dynamsoft Standard Camera Input 

1. Add `CameraView` to your layout.

   ```xml
   <com.dynamsoft.dce.CameraView
       android:id="@+id/camera_view"
       android:layout_width="match_parent"
       android:layout_height="match_parent"/>
   ```

2. Create a `CameraEnhancer` object and bind it to `CameraView`.

   <div class="sample-code-prefix"></div>
   >- Java
   >- Kotlin
   >
   >1.
   ```java
   CameraEnhancer mCamera;
   CameraView cameraView = findViewById(R.id.camera_view);
   mCamera = new CameraEnhancer(cameraView, this);
   ```
   2.
   ```kotlin
   val cameraView: CameraView = findViewById(R.id.camera_view)
   val mCamera = CameraEnhancer(cameraView, this)
   ```

3. Use `CaptureVisionRouter.setInput` to set the `CameraEnhancer` object as the input source.

   <div class="sample-code-prefix"></div>
   >- Java
   >- Kotlin
   >
   >1.
   ```java
   CaptureVisionRouter mRouter;
   mRouter = new CaptureVisionRouter();
   try {
       mRouter.setInput(mCamera);
   } catch (CaptureVisionRouterException e) {
       throw new RuntimeException(e);
   }
   ```
   2.
   ```kotlin
   val mRouter = CaptureVisionRouter()
   try {
       mRouter.setInput(mCamera)
   } catch (e: CaptureVisionRouterException) {
       throw RuntimeException(e)
   }
   ```

### Other Camera Input

> Note:
> If you are using CameraX, refer to the [`DecodeWithCameraX`](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/android/FoundationalAPISamples/DecodeWithCameraX) sample for camera input integration.

To use another camera source, complete the following steps so the library can process the input:

1. Receive the camera input.
2. Convert the raw camera input to a `com.dynamsoft.core.basic_structures.ImageData` object.
3. Use `addImageToBuffer` to add the `ImageData` object to the buffer. 

## Result receiver

Use `CapturedResultReceiver` to receive capture results. The callback is triggered each time an image is processed, regardless of whether a barcode is decoded.

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1.
```java
mRouter.addResultReceiver(new CapturedResultReceiver() {
    @Override
    public void onDecodedBarcodesReceived(@NonNull DecodedBarcodesResult result) {
    }
});
```
2.
```kotlin
mRouter.addResultReceiver(object : CapturedResultReceiver {
    override fun onDecodedBarcodesReceived(result: DecodedBarcodesResult) {
    }
})
```

## Start capturing

Use `startCapturing` and `stopCapturing` to control when barcode decoding starts and stops.

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1.
```java
mRouter.startCapturing("ReadBarcodes_Default", new CompletionListener() {
    @Override
    public void onSuccess() {
    }
    @Override
    public void onFailure(int errorCode, String errorString) {
    }
});
```
2.
```kotlin
mRouter.startCapturing("ReadBarcodes_Default", object : CompletionListener {
    override fun onSuccess() {
    }
    override fun onFailure(errorCode: Int, errorString: String?) {
    }
})
```
