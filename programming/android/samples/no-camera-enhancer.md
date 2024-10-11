---
layout: default-layout
title: Decode with CameraX - Dynamsoft Barcode Reader for Android
description: This is a guide on how to use the Android Barcode Reader with the CameraX component instead of Camera Enhancer.
keywords: sample, Android, CameraX
needAutoGenerateSidebar: true
breadcrumbText: No Camera Enhancer
permalink: /programming/android/samples/no-camera-enhancer.html
ignore: true
---

# Decode from Video Sample - Use CameraX as Image Source

`DecodeWithCameraX` is another sample of recognizing barcodes from the video streaming. In this sample, instead of `DynamsoftCameraEnhancer`, `CameraX` is used to implement the [`ImageSourceAdapter`]({{ site.dcv_android_api }}core/basic-structures/image-source-adapter.html) (ISA) so that the `CaptureVisionRouter` is able to fetch the video frames.

**View the sample code**

* <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/android/HelloWorld/DecodeWithCameraX/" target="_blank">Java DecodeWithCameraX Sample</a>
* <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/android/HelloWorld/DecodeWithCameraXKt/" target="_blank">Kotlin DecodeWithCameraX Sample</a>

## Generate ImageData from ImageAnalysisAnalyzer

[`ImageData`]({{ site.dcv_android_api }}core/basic-structures/image-data.html) is the standard image data type that can be recognized by Dynamsoft SDKs. [`ISA`]({{ site.dcv_android_api }}core/basic-structures/image-source-adapter.html) is the interface that maintains a video buffer of the `ImageData` and deliver the `ImageData` objects to Dynamsoft image processing SDKs.

* Create a Class for implementing the video streaming functions with `CameraX`.
* Let your class extend `ImageSourceAdapter` so that you can use ISA APIs.
* Receive video frames from `ImageAnalysisAnalyzer` and generate the image data to `ImageData` object.
* Send the `ImageData` to the ISA with its `addImageToBuffer` method. After that the `ImageData` will be maintained in the video buffer of the ISA.

The following code snippet shows how to generate `ImageData` from the `ImageAnalysisAnalyzer`

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
lifecycleCameraController.setImageAnalysisAnalyzer(Executors.newSingleThreadExecutor(), image -> {
    try {
        if (mBytes == null || mBytes.length != image.getPlanes()[0].getBuffer().remaining()) {
            mBytes = new byte[image.getPlanes()[0].getBuffer().remaining()];
        }
        image.getPlanes()[0].getBuffer().get(mBytes);
        int nRowStride = image.getPlanes()[0].getRowStride();
        int nPixelStride = image.getPlanes()[0].getPixelStride();
        ImageData imageData = new ImageData();
        imageData.bytes = mBytes;
        imageData.width = image.getWidth();
        imageData.height = image.getHeight();
        imageData.stride = nRowStride;
        imageData.format = EnumImagePixelFormat.IPF_NV21;
        imageData.orientation = image.getImageInfo().getRotationDegrees();
        addImageToBuffer(imageData);
    } finally {
        image.close();
    }
});
```
2. 
```kotlin
lifecycleCameraController.setImageAnalysisAnalyzer(
    Executors.newSingleThreadExecutor()
) { image: ImageProxy ->
    try {
        if (mBytes == null || mBytes!!.size != image.planes[0].buffer
                .remaining()
        ) {
            mBytes = ByteArray(image.planes[0].buffer.remaining())
        }
        image.planes[0].buffer[mBytes!!]
        val nRowStride = image.planes[0].rowStride
        val nPixelStride = image.planes[0].pixelStride
        val imageData = ImageData()
        imageData.bytes = mBytes
        imageData.width = image.width
        imageData.height = image.height
        imageData.stride = nRowStride
        imageData.format = EnumImagePixelFormat.IPF_NV21
        imageData.orientation = image.imageInfo.rotationDegrees
        addImageToBuffer(imageData)
    } finally {
        image.close()
    }
}
```

## Setup CaptureVisionRouter with the ISA You Implemented Above

The following code snippet show how to bind the `ISA` you implemented above to the `CaptureVisionRouter` and start barcode decoding.

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
public class MainActivity extends AppCompatActivity {
    private CaptureVisionRouter mRouter;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        ...
        // Initialize the class you created above.
        CameraXImageSourceAdapter cameraXImageSourceAdapter = new CameraXImageSourceAdapter(this, this, findViewById(R.id.previewView));
        mRouter = new CaptureVisionRouter(this);
        try {
            // Bind the `capture` as an ISA instance to your CaptureVisionRouter.
            mRouter.setInput(cameraXImageSourceAdapter);
        } catch (CaptureVisionRouterException e) {
            throw new RuntimeException(e);
        }
        // Add CapturedResultReceiver to receive barcode decoding results.
        mRouter.addResultReceiver(new CapturedResultReceiver() {
            @Override
            public void onDecodedBarcodesReceived(DecodedBarcodesResult result) {
                // Add code to do when barcode decoding results are received.
            }
        });
    }
    @Override
    protected void onResume() {
        super.onResume();
        // Start capturing.
        mRouter.startCapturing(EnumPresetTemplate.PT_READ_BARCODES, null);
    }
}
```
2. 
```kotlin
class MainActivity : AppCompatActivity() {
    private var mRouter: CaptureVisionRouter? = null
    override fun onCreate(savedInstanceState: Bundle?) {
        ...
        // Initialize the class you created above.
        val cameraXImageSourceAdapter =
            CameraXImageSourceAdapter(this, this, findViewById(R.id.previewView))
        mRouter = CaptureVisionRouter(this)
        try {
            // Bind the `capture` as an ISA instance to your CaptureVisionRouter.
            mRouter!!.input = cameraXImageSourceAdapter
        } catch (e: CaptureVisionRouterException) {
            throw RuntimeException(e)
        }
        // Add CapturedResultReceiver to receive barcode decoding results.
        mRouter!!.addResultReceiver(object : CapturedResultReceiver {
            override fun onDecodedBarcodesReceived(result: DecodedBarcodesResult) {
                // Add code to do when barcode decoding results are received.
            }
        })
    }
    override fun onResume() {
        super.onResume()
        // Start capturing.
        mRouter!!.startCapturing(EnumPresetTemplate.PT_READ_BARCODES, null)
    }
}
```
