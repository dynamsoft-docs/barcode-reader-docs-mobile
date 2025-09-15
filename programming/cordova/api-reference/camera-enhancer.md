---
layout: default-layout
title: Class DCVCameraEnhancer of Dynamsoft Capture Vision Cordova Edition
description: This page is the API reference of Class DCVCameraEnhancer
keywords: Class DCVCameraEnhancer, API Reference, Cordova
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: DCVCameraEnhancer
---

# Class DCVCameraEnhancer

The interface `DCVCameraEnhancer` provides camera and camera related hardware controlling APIs.

```js
class DCVCameraEnhancer
```

| Method | Description |
| ------ | ----------- |
| [`createInstance`](#createinstance) | Create an instance of `DCVCameraEnhancer`. |
| [`setScanRegion`](#setscanregion) | Specify the region of interest. |
| [`open`](#open) | Open the camera. |
| [`close`](#close) | Close the camera. |
| [`turnOnTorch`](#turnontorch) | Turn on the torch. |
| [`turnOffTorch`](#turnofftorch) | Turn off the torch. |

## createInstance

Create an instance of `DCVCameraEnhancer`.

```js
static createInstance(): Promise<DCVCameraEnhancer>;
```

**Return Value**

An instance of `DCVCameraEnhancer`.

**Code Snippet**

```js
dce = await Dynamsoft.DCVCameraEnhancer.createInstance()
```

## setScanRegion

Specify a region of interest.

```js
setScanRegion(region: Region): Promise<void>;
```

**Parameters**

`region`: An object of `Region` class. It contains the coordinates of the top, bottom, left and right border of the region. View more in [`Region`](interface-region.md).

**Code Snippet**

```js
dce.setScanRegion({
    regionLeft: 15,
    regionRight: 85,
    regionTop: 30,
    regionBottom: 70,
    regionMeasuredByPercentage: true
})
```

**Related APIs**

- [Region](interface-region.md)

## open

Open the camera.

```js
open(): Promise<void>;
```

## close

Close the camera.

```js
close(): Promise<void>;
```

## turnOnTorch

Turn on the torch.

```js
turnOnTorch(): Promise<void>;
```

## turnOffTorch

Turn off the torch.

```js
turnOffTorch(): Promise<void>;
```
