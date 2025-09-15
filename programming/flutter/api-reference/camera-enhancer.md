---
layout: default-layout
title: DCVCameraEnhancer Class of Dynamsoft Capture Vision Flutter Edition
description: This page is the API reference of DCVCameraEnhancer class
keywords: Camera enhancer, API reference, Flutter
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: DCVCameraEnhancer class
---

# DCVCameraEnhancer Class

The class provides camera control APIs.

| Property | Description |
| -------- | ----------- |
| [`createInstance`](#createinstance) | Create a camera enhancer instance. |
| [`open`](#open) | Open the camera. |
| [`close`](#close) | Close the camera. |
| [`selectCamera`](#selectcamera) | Select a camera (front-facing or back-facing camera). |
| [`turnOnTorch`](#turnofftorch) | Turn on the torch. |
| [`turnOffTorch`](#turnofftorch) | Turn off the torch. |
| [`setScanRegion`](#setscanregion) | The property for users to specify the region of interest. |

## createInstance

Create a camera enhancer instance.

```dart
static Future<DCVCameraEnhancer> createInstance() async;
```

**Return Value**

A camera enhancer instance.

**Code Snippet**

```dart
late final DCVCameraEnhancer _cameraEnhancer;
_cameraEnhancer = await DCVCameraEnhancer.createInstance();
```

## open

Open the camera.

```dart
Future open()
```

## close

Close the camera.

```dart
Future close()
```

## selectCamera

Select a camera (front-facing or back-facing camera).

```dart
Future selectCamera(EnumCameraPosition position)
```

**Parameters**

`position`: A Enumeration value that specify the camera position. User can either select the front facing camera or the back-facing camera.

**Code Snippet**

```dart
late final DCVCameraEnhancer _cameraEnhancer;
_cameraEnhancer = await DCVCameraEnhancer.createInstance();
await _cameraEnhancer.selectCamera(EnumCameraPosition.CP_FRONT)
```

## turnOnTorch

Turn on the torch.

```dart
Future turnOnTorch()
```

**Code Snippet**

```dart
// Turn on the torch
_cameraEnhancer.turnOnTorch();
// Turn off the torch
_cameraEnhancer.turnOffTorch();
```

## turnOffTorch

Turn off the torch.

```dart
Future turnOffTorch()
```

## setScanRegion

The property for users to specify the region of interest.

```dart
Future setScanRegion(Region scanRegion)
```

**Code Snippet**

```dart
final DCVCameraEnhancer _cameraEnhancer = await DCVCameraEnhancer.createInstance();
Region scanRegion = Region(regionTop: 20, regionBottom: 80, regionLeft: 20, regionRight: 80, regionMeasuredByPercentage: true);
_cameraEnhancer.setScanRegion(scanRegion);
```
