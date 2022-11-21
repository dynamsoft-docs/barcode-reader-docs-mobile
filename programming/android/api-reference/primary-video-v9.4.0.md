---
layout: default-layout
title: Dynamsoft Barcode Reader Android API Reference - Camera Methods
description: Follow this API reference to learn how to decode barcodes from video streaming on Android.
keywords: Camera methods, BarcodeReader, api reference, android
needAutoGenerateSidebar: true
noTitleIndex: true
pageStartVer: 8.6
permalink: /programming/android/api-reference/primary-video.html
---


# Video Decoding Methods

> Note:
>  
> - You have to include `CameraEnhancer` when using **Video Decoding Methods**.  
> - `CameraEnhancer` provide APIs that help you quickly deploy a camera module and capture video streaming for barcode decoding.  
> - Through **Video Decoding Methods** you can control whether to start video streaming barcode decoding and get the barcode results.  
> - Be sure that your `BarcodeReader` version is **8.9.0+** and `CameraEnhancer` is **2.1.0+** when using the methods on this page.

| Method | Description |
|--------|-------------|
| [`setCameraEnhancer`](#setcameraenhancer) | Bind a Camera Enhancer instance to the Barcode Reader.  |
| [`startScanning`](#startscanning) | Start the barcode reading thread. |
| [`stopScanning`](#stopscanning) | Stop the barcode reading thread. |
| [`setTextResultListener`](#settextresultlistener) | Set callback interface to process text results generated during frame decoding. |
| [`setIntermediateResultListener`](#setintermediateresultlistener) | Set callback interface to process intermediate results generated during frame decoding. |
| [`setMinImageReadingInterval`](#setminimagereadinginterval) | Set the minimum interval between two barcode decoding. |
| [`getMinImageReadingInterval`](#getminimagereadinginterval) | Get the minimum interval between two barcode decoding. |
| [`setImageSource`](#setimagesource) | Set the ImageSource as the source of video streaming. |
| [`enableResultVerification`](#enableresultverification) | Result will be verified before output. |
| [`enableDuplicateFilter`](#enableduplicatefilter) | Filter out the duplicate results in the period of `duplicateForgetTime` for video barcode decoding. Barcode results with the same text and format will be returned only once during the period. |

---

## setCameraEnhancer

Bind a `Dynamsoft Camera Enhancer` instance to the Barcode Reader. `Dynamsoft Camera Enhancer` is designed for video streaming processing scenarios. It can help the Barcode Reader to acquire video frames continuously for video streaming barcode decoding.

```java
void setCameraEnhancer(CameraEnhancer mCameraEnhancer)
```

**Parameters**

`mCameraEnhancer`: An instance of `Dynamsoft Camera Enhancer`.

**Code Snippet**

This code snippet displays a complete code on how to add CameraEnhancer to your project and start to use Video Decoding Methods to decode and get barcode results from the video streaming.

```java
BarcodeReader reader;
CameraEnhancer mCameraEnhancer;
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setContentView(R.layout.activity_main);

    // Be sure that you have added a cameraView in the layout file.
    DCECameraView cameraView = findViewById(R.id.cameraView);
    try {
        // Create an instance of Dynamsoft Barcode Reader.
        reader = new BarcodeReader();
    } catch (BarcodeReaderException e) {
        e.printStackTrace();
    }
    mCameraEnhancer = new CameraEnhancer(MainActivity.this);
    mCameraEnhancer.setCameraView(cameraView);

    // Bind the Camera Enhancer instance to the Barcode Reader instance.
    reader.setCameraEnhancer(mCameraEnhancer);

    // Result callback configurations
    TextResultListener mTextResultListener = new TextResultListener() {
        // Obtain the recognized barcode results and display.
        @Override
        public void textResultCallback(int id, ImageData imageData, TextResult[] textResults) {
            // Add your code to execute when barcode results are returned.
        }
    };
    reader.setTextResultListener(mTextResultListener);
}
@Override
public void onResume() {
    // Open the camera and start video barcode reading
    try {
        mCameraEnhancer.open();
    } catch (CameraEnhancerException e) {
        e.printStackTrace();
    }
    reader.startScanning();
    super.onResume();
}

@Override
public void onPause() {
    // Stop video barcode reading
    try {
        mCameraEnhancer.close();
    } catch (CameraEnhancerException e) {
        e.printStackTrace();
    }
    reader.stopScanning();
    super.onPause();
}
```

## startScanning

Start the video streaming barcode decoding thread. Please be sure that you have bound a `CameraEnhancer` or `ImageSource` to the barcode reader before you trigger `startScanning`.

```java
void startScanning()
```

**Code Snippet**

You can view the complete code snippet in [`setCameraEnhancer`](#setcameraenhancer).

## stopScanning

Stop the video streaming barcode decoding thread.

```java
void stopScanning()
```

**Code Snippet**

You can view the complete code snippet in [`setCameraEnhancer`](#setcameraenhancer).

## setTextResultListener

Set a callback interface to process text results generated during frame decoding.

```java
void setTextResultListener(TextResultListener textResultListener)
```

**Parameters**

`textResultCallback`: Callback interface.

**Code Snippet**

You can view the complete code snippet in [`setCameraEnhancer`](#setcameraenhancer).

## setIntermediateResultListener

Set a callback interface to process intermediate results generated during frame decoding.

```java
void setIntermediateResultListener(IntermediateResultListener intermediateResultListener)
```

**Parameters**

`intermediateResultCallback`: Callback interface.

**Code Snippet**

The usage of `intermediateResultListener` is similar to the `textResultListener`. You can view detailed code snippet in [`setCameraEnhancer`](#setcameraenhancer) and replace the `textResultListener` code with the `intermediateResultListener` code.

```java
BarcodeReader reader = new BarcodeReader();
PublicRuntimeSettings settings = reader.getRuntimeSettings();
// You can set intermediateResult type when using intermediateResultListener
settings.intermediateResultTypes = EnumIntermediateResultType.IRT_ORIGINAL_IMAGE | EnumIntermediateResultType.IRT_COLOUR_CLUSTERED_IMAGE | EnumIntermediateResultType.IRT_COLOUR_CONVERTED_GRAYSCALE_IMAGE;
reader.updateRuntimeSettings(settings);
reader.setIntermediateResultListener(new IntermediateResultListener() {
    @Override
    public void intermediateResultCallback(int i, ImageData imageData, IntermediateResult[] intermediateResults) {
        //TODO add your code for using intermediate results           
    }
});
```

## setMinImageReadingInterval

Set the minimum interval between two barcode decoding. The unit of measure for this property is milliseconds. If the previous barcode decoding is finished in `n` milliseconds (`n` < `minImageReadingInterval`), the barcode decoding thread will be paused by `minImageReadingInterval` - `n` milliseconds.

```java
void setMinImageReadingInterval(int interval);
```

**Parameters**

`interval`: The minimum interval between two barcode decoding. The value is measured by millisecond.

**Code Snippet**

```java
reader.setMinImageReadingInterval(500);
```

## getMinImageReadingInterval

Get the minimum interval between two barcode decoding.

```java
int getMinImageReadingInterval();
```

**Return Value**

The current minimum interval setting.

**Code Snippet**

```java
int interval = reader.getMinImageReadingInterval();
```

## setImageSource

Set the ImageSource as the source of video streaming.

```java
void setImageSource(ImageSource source);
```

**Parameters**

`source`: The source of images

**Code Snippet**

Here we use CameraX as the example of the image source. The following code displays how to use CameraX to capture video frames and tranfer the video frames into [`ImageData`](auxiliary-ImageData.md).

```java
private ImageData mImageData;
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setContentView(R.layout.activity_main);
    try {
        mReader = new BarcodeReader();
    } catch (BarcodeReaderException e) {
        e.printStackTrace();
    }
    // Set image source
    mReader.setImageSource(new ImageSource() {
        @Override
        // Configure the getImage method.
        public ImageData getImage() {
            return mImageData;
        }
    });
    // Configure the listener to receive the TextResult from the textResultCallback
    mReader.setTextResultListener(new TextResultListener() {
        @Override
        public void textResultCallback(int i, ImageData imageData, TextResult[] textResults) {
            // Add your code to execute when iTextResult is received.
        }
    }
}
// onResume start barcode decoding.
@Override
protected void onResume() {
    super.onResume();
    mReader.startScanning();
}
// onPause stop barcode decoding.
@Override
protected void onPause() {
    super.onPause();
    mReader.stopScanning();
}
// Get the buffer image from CameraX Analyzer and generate the image into iImageData.
private ImageAnalysis.Analyzer mBarcodeAnalyzer = new ImageAnalysis.Analyzer() {
    @Override
    public void analyze(@NonNull ImageProxy imageProxy) {
        try {
            if(isShowingDialog) {
                mImageData = null;
                return;
            }
            byte[] data = new byte[imageProxy.getPlanes()[0].getBuffer().remaining()];
            imageProxy.getPlanes()[0].getBuffer().get(data);
            int nRowStride = imageProxy.getPlanes()[0].getRowStride();
            int nPixelStride = imageProxy.getPlanes()[0].getPixelStride();
            ImageData imageData = new ImageData();
            imageData.bytes = data;
            imageData.width = imageProxy.getWidth();
            imageData.height = imageProxy.getHeight();
            imageData.stride = nRowStride;
            imageData.format =EnumImagePixelFormat.IPF_NV21;
            imageData.orientation = imageProxy.getImageInfo().getRotationDegrees();
            mImageData = imageData;
        } finally {
            imageProxy.close();
        }
    }
};
```

## enableResultVerification

Enable **Result Verification** feature to improve the accuracy of barcode results for video streaming barcode decoding. This feature is not enabled by default.

There are 2 way for you to get barcode results:

- From the return value of [`decode`](primary-decode.md) methods when processing a single image.
- From the [`textResultCallback`](interface-textresultcallback.md) when processing the video streaming.

**Result verification** feature only effects on the **OneD barcode** results you get from `textResultCallback`.

```java
void enableResultVerification(boolean)
```

**Code Snippet**

```java
reader.enableResultVerification(true)
// To check the status of this mode:
boolean x = reader.getEnableResultVerificationStatus();
```

## enableDuplicateFilter

Enable **Duplicate Filter** feature to filter out the duplicate results in the period of 3000ms for video barcode decoding. Barcode results with the same text and format will be returned only once during the period.

There are 2 way for you to get barcode results:

- From the return value of [`decode`](primary-decode.md) methods when processing a single image.
- From the [`textResultCallback`](interface-textresultcallback.md) when processing the video streaming.

**Duplicate filter** only effects on the duplicate results that output by `textResultCallback`.

```java
void enableDuplicateFilter(boolean)
```

**Code Snippet**

```java
reader.enableDuplicateFilter(true)
```
