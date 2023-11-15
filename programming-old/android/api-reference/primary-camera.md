---
layout: default-layout
title: Camera Methods - Dynamsoft Barcode Reader Android API Reference
description: Follow this API reference to learn how to control the camera enhancer via Dynamsoft Barcode Reader APIs on Android.
keywords: Camera methods, BarcodeReader, api reference, android
needAutoGenerateSidebar: true
noTitleIndex: true
pageStartVer: 8.6
permalink: /programming/android/api-reference/primary-camera.html
---


# Camera Methods

> Note:  
>  
> - This class is removed in 9.0 version. Please use the [video methods](primary-video.html) for video barcode scanning if you are using the latest version.

| Method | Description |
|--------|-------------|
| [`StartCameraEnhancer`](#startcameraenhancer) | Start using Dynamsoft Camera Enhancer |
| [`StopCameraEnhancer`](#stopcameraenhancer) | Stop using Dynamsoft Camera Enhancer |
| [`PauseCameraEnhancer`](#pausecameraenhancer) | Pause the process of Dynamsoft Camera Enhancer |
| [`ResumeCameraEnhancer`](#resumecameraenhancer) | Pause the process of Dynamsoft Camera Enhancer |
| [`SetCameraEnhancerParam`](#setcameraenhancerparam) | Set the parameters for Dynamsoft Camera Enhancer in Barcode reader |

This page illustrates the controlling of `Dynamsoft Camera Enhancer`. To get a better understanding of this section, please read more about [`Dynamsoft Camera Enhancer`](https://www.dynamsoft.com/camera-enhancer/docs/mobile/programming/android/).

## StartCameraEnhancer

The API that controlling the start of `Dynamsoft Camera Enhancer`.

```java
void StartCameraEnhancer()
```

**Code Snippet**

```java
reader.StartCameraEnhancer();
```

## StopCameraEnhancer

The API that controlling the start of `Dynamsoft Camera Enhancer`.

```java
void StopCameraEnhancer()
```

**Code Snippet**

```java
reader.StopCameraEnhancer();
```

## PauseCameraEnhancer

The API that controlling the pause of `Dynamsoft Camera Enhancer`.

```java
void com.dynamsoft.dbr.BarcodeReader.PauseCameraEnhancer()
```

**Code Snippet**

```java
reader.PauseCameraEnhancer();
```

## ResumeCameraEnhancer

The API that controlling the resume of `Dynamsoft Camera Enhancer`.

```java
void ResumeCameraEnhancer()
```

**Code Snippet**

```java
reader.ResumeCameraEnhancer();
```

## SetCameraEnhancerParam

Set the CameraEnhancer parameters.

```java
void SetCameraEnhancerParam(DCESettingParameters _param)
```

**Parameters**

`cameraInstance`: The instance of Dynamsoft Camera Enhancer.  
[`TextResultCallback`](interface-textresultcallback-v8.9.3.html): The text result callback.  
[`intermediateResultCallback`](interface-intermediateresultcallback-v8.9.3.html): The intermediate result callback.

**Code Snippet**

```java
DCESettingParameters dceSettingParameters = new DCESettingParameters();
dceSettingParameters.cameraInstance = mCameraEnhancer;
dceSettingParameters.textResultCallback = mTextResultCallback;
dceSettingParameters.intermediateResultCallback = mIntermediateResultCallback;
reader.SetCameraEnhancerParam(dceSettingParameters);
```

**See Also**

[`DCESettingParameters`](auxiliary-DCESettingParameters.html): The parameters that will be used in `SetCameraEnhancerParam`.
