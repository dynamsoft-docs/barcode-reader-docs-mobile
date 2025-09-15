---
layout: default-layout
title: LineSegment Class - Dynamsoft Barcode Reader Android API Reference
description: This page shows the LineSegment Class of Dynamsoft Barcode Reader for Android SDK.
keywords: LineSegment, class, api reference, android
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
ignore: true
permalink: /programming/android/api-reference/auxiliary-LineSegment.html
---

# LineSegment

Stores line segment data.

```java
class com.dynamsoft.dbr.LineSegment;
```

| Attribute | Type | Descriptions |
|---------- | ---- | ----------- |
| [`startPoint`](#startpoint) | [`Point`](auxiliary-Point.html) | The start point of the line segment. |
| [`endPoint`](#endpoint) | [`Point`](auxiliary-Point.html) | The end point of the line segment. |
| [`linesConfidenceCoefficients`](#linesconfidencecoefficients) | *byte\[\]* | The confidence coefficients for lines. |

## startPoint

The start point of the line segment.

```java
Point[] startPoint
```

## endPoint

The end point of the line segment.

```java
Point[] endPoint
```

## linesConfidenceCoefficients

The confidence coefficients for lines. There are 4 coefficients in this set:  

1. linesConfidenceCoefficients\[0\] is average positive amplitude;
2. linesConfidenceCoefficients\[1\] is max positive amplitude;
3. linesConfidenceCoefficients\[2\] is average negative amplitude;
4. linesConfidenceCoefficients\[3\] is max negative amplitude.

```java
byte[] linesConfidenceCoefficients
```
