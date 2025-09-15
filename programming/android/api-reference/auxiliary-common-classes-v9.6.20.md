---
layout: default-layout
title: Common Classes - Dynamsoft Barcode Reader Android API Reference
description: The common classes of Dynamsoft Barcode Reader SDK Android edition such as point, quadrilateral, & region definition.
keywords: Common Classes, API reference, android
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
permalink: /programming/android/api-reference/auxiliary-common-classes-v9.6.20.html
---

# Common Classes

## [Point](auxiliary-Point.html)

The point class Stores the x and y coordinate of the points.

```java
class com.dynamsoft.dbr.Point;
```

| Attribute | Type | Descriptions |
|---------- | ---- | ------------ |
| [`x`](auxiliary-Point.html#x) | *int* | The X coordinate of the point. |
| [`y`](auxiliary-Point.html#y) | *int* | The y coordinate of the point. |

## [Quadrilateral](auxiliary-Quadrilateral.html)

This class stores the quadrilateral points data.

```java
class com.dynamsoft.dbr.Quadrilateral;
```

| Attribute | Type | Descriptions |
|---------- | ---- | ------------ |
| [`points`](auxiliary-Quadrilateral.html#points) | [`Point`](auxiliary-Point.html)[] | Four vertexes in a clockwise direction of a quadrilateral. Index 0 represents the left-most vertex. |

## [RegionDefinition](auxiliary-RegionDefinition.html)

This class stores the region data. You can make settings on scan region through this class.

```java
class com.dynamsoft.dbr.RegionDefinition;
```

| Attribute | Type | Descriptions |
|---------- | ---- | ------------ |
| [`regionTop`](auxiliary-RegionDefinition.html#regiontop) | *int* | The top-most coordinate or percentage of the region. |
| [`regionLeft`](auxiliary-RegionDefinition.html#regionleft) | *int* | The left-most coordinate or percentage of the region. |
| [`regionRight`](auxiliary-RegionDefinition.html#regionright) | *int* | The right-most coordinate or percentage of the region. |
| [`regionBottom`](auxiliary-RegionDefinition.html#regionbottom) | *int* | The bottom-most coordinate or percentage of the region. |
| [`regionMeasuredByPercentage`](auxiliary-RegionDefinition.html#regionmeasuredbypercentage) | *int* | Sets whether or not to use percentage to measure the region size. |
