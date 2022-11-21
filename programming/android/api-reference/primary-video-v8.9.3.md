---
layout: default-layout
title: Dynamsoft Barcode Reader Android API Reference - Camera Methods
description: This page shows Camera methods of Dynamsoft Barcode Reader for Android SDK.
keywords: Camera methods, BarcodeReader, api reference, android
needAutoGenerateSidebar: true
noTitleIndex: true
pageStartVer: 8.6
permalink: /programming/android/api-reference/primary-video-v8.9.3.html
---


# Video Decoding Methods

| Method | Description |
|--------|-------------|
| [`setCameraEnhancer`](#setcameraenhancer) | Bind a Camera Enhancer instance to the Barcode Reader.  |
| [`startScanning`](#startscanning) | Start the barcode reading thread. |
| [`stopScanning`](#stopscanning) | Stop the barcode reading thread. |
| [`setTextResultCallback`](#settextresultcallback) | Set callback interface to process text results generated during frame decoding. |
| [`setIntermediateResultCallback`](#setintermediateresultcallback) | Set callback interface to process intermediate results generated during frame decoding. |
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

```java
BarcodeReader reader = new BarcodeReader();
CameraEnhancer mCameraEnhancer = new CameraEnhancer(MainActivity.this);
mCameraEnhancer.setCameraView(cameraView);
reader.setCameraEnhancer(mCameraEnhancer);
```

## startScanning

Start the video streaming barcode decoding thread. Please be sure that you have bound a Camera Enhancer to the barcode reader before you trigger `startScanning`.

```java
void startScanning()
```

**Code Snippet**

```java
BarcodeReader reader = new BarcodeReader();
reader.startScanning();
```

## stopScanning

Stop the video streaming barcode decoding thread.

```java
void stopScanning()
```

**Code Snippet**

```java
BarcodeReader reader = new BarcodeReader();
reader.stopScanning();
```

## setTextResultCallback

Set a callback interface to process text results generated during frame decoding.

```java
void setTextResultCallback(TextResultCallback textResultCallback, Object userData) throws BarcodeReaderException
```

**Parameters**

`textResultCallback`: Callback interface.  
`userData`: Customized arguments passed to your function.

**Exceptions**

[`BarcodeReaderException`](auxiliary-BarcodeReaderException.md)

**Code Snippet**

```java
BarcodeReader reader = new BarcodeReader();
reader.setTextResultCallback(new TextResultCallback() {
    @Override
    public void textResultCallback(int frameId, TextResult[] results, Object userData) {
        //TODO add your code for using text results
    }
}, null);
```

## setIntermediateResultCallback

Set a callback interface to process intermediate results generated during frame decoding.

```java
void setIntermediateResultCallback(IntermediateResultCallback intermediateResultCallback, Object userData} throws BarcodeReaderException
```

**Parameters**

`intermediateResultCallback`: Callback interface.  
`userData`: Customized arguments passed to your function.

**Exceptions**

[`BarcodeReaderException`](auxiliary-BarcodeReaderException.md)

**Code Snippet**

```java
BarcodeReader reader = new BarcodeReader();
PublicRuntimeSettings settings = reader.getRuntimeSettings();
settings.intermediateResultTypes = EnumIntermediateResultType.IRT_ORIGINAL_IMAGE | EnumIntermediateResultType.IRT_COLOUR_CLUSTERED_IMAGE | EnumIntermediateResultType.IRT_COLOUR_CONVERTED_GRAYSCALE_IMAGE;
reader.updateRuntimeSettings(settings);
reader.setIntermediateResultCallback(new IntermediateResultCallback() {
    @Override
    public void intermediateResultCallback(int frameId, IntermediateResult[] results, Object userData) {
        //TODO add your code for using intermediate results
    }
}, null);
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
