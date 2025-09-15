---
layout: default-layout
title: FrameDecodingParameters Class - Dynamsoft Barcode Reader Android API Reference
description: This page shows the FrameDecodingParameters Class of Dynamsoft Barcode Reader for Android SDK.
keywords: FrameDecodingParameters, class, api reference, android
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
permalink: /programming/android/api-reference/auxiliary-FrameDecodingParameters-v8.9.3.html
---

# FrameDecodingParameters

> Note:  
>
> - This class is removed in 9.0 version. Please use the [video methods](primary-video.html) for video barcode scanning if you are using the latest version.

Defines a struct to configure the frame decoding Parameters.  

```java
class com.dynamsoft.dbr.FrameDecodingParameters
```

| Attribute | Type | Descriptions |
|---------- | ---- | ------------ |
| [`maxQueueLength`](#maxqueuelength) | *int* | The maximum number of frames waiting for decoding. |
| [`maxResultQueueLength`](#maxresultqueuelength) | *int* | The maximum number of frames waiting results (text result/localization result) will be kept for further reference. |
| [`width`](#width) | *int* | The width of the frame image in pixels.  |
| [`height`](#height) | *int* | The height of the frame image in pixels. |
| [`stride`](#stride) | *int* | The stride (or scan width) of the frame image. |
| [`imagePixelFormat`](#imagepixelformat) | *int* | The image pixel format used in the image byte array. |
| [`region`](#region) | `RegionDefinition` | The region definition of the frame to calculate the internal indicator. |
| [`threshold`](#threshold) | *float* | The threshold used for filtering frames. |
| [`fps`](#fps) | *int* | The frequency of calling `appendFrame` per second. |
| [`autoFilter`](#autofilter) | *int* | Sets whether to filter frames automatically. |
| [`clarityCalculationMethod`](#claritycalculationmethod) | *int* | Sets the method used for calculating the clarity of the frames. |
| [`clarityFilterMode`](#clarityfiltermode) | *int* | Sets the mode used for filtering frames by calculated clarity. |

## maxQueueLength

The maximum number of frames waiting for decoding.

```java
int maxQueueLength
```

**Value Range**

[0,0x7fffffff]

**Default Value**

3

## maxResultQueueLength

The maximum number of frames waiting results (text result/localization result) will be kept for further reference.  

```java
int maxResultQueueLength
```

**Value Range**

[0,0x7fffffff]

**Default Value**

10  

## width

The width of the frame image in pixels.

```java
int width
```

**Value Range**

[0,0x7fffffff]

**Default Value**

0  

## height

The height of the frame image in pixels.

```java
int height
```

**Value Range**

[0,0x7fffffff]

**Default Value**

0  

## stride

The stride (or scan width) of the frame image.

```java
int stride
```

**Value Range**

[0,0x7fffffff]

**Default Value**

0

## imagePixelFormat

The image pixel format used in the image byte array.

```java
int imagePixelFormat
```

**Value Range**

A value of `EnumImagePixelFormat` Enumeration items.

**Default Value**

`IPF_GRAYSCALED`

**See Also**

`EnumImagePixelFormat`

## region

The region definition of the frame to calculate the internal indicator.  

```java
RegionDefinition region
```

**Default Value**

`{ regionLeft = 0, regionRight = 100, regionTop = 0, regionBottom = 100, regionMeasuredByPercentage = 1 }`

**See Also**

`RegionDefinition`

## threshold

The threshold used for filtering frames.

```java
float threshold
```

**Value Range**

[0, 1]

**Default Value**

0.1

**Remarks**

The SDK will calculate an inner indicator for each frame from `appendFrame`, if the change rate of the indicators between the current frame and the history frames is larger than the given threshold, the current frame will not be added to the inner frame queue waiting for decoding.

## fps

The frequency of calling `appendFrame` per second.

```java
int fps
```

**Value Range**

[0,0x7fffffff]

**Default Value**

0  

**Remarks**

0 means the frequency will be calculated automatically by the SDK.

## autoFilter

Sets whether to filter frames automatically.

```java
int autoFilter
```

**Value Range**

[0,1]

**Default Value**

1  

**Remarks**

0: Diable filtering frames automatically. 1: Enable filtering frames automatically.

## clarityCalculationMethod

Sets the method used for calculating the clarity of the frames.

```java
int clarityCalculationMethod
```

**Value Range**

Any one of the `EnumClarityCalculationMethod` Enumeration items.

**Default Value**

ECCM_CONTRAST

**See Also**

`EnumClarityCalculationMethod`

## clarityFilterMode

Sets the mode used for filtering frames by calculated clarity.

```java
int clarityFilterMode
```

**Value Range**

Any one of the `EnumClarityFilterMode` Enumeration items.

**Default Value**

CFM_GENERAL

**See Also**

`EnumClarityFilterMode`
