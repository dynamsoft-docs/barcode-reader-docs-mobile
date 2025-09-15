---
layout: default-layout
title: DCESettingParameters Class - Dynamsoft Barcode Reader Android API Reference
description: This page shows the DCESettingParameters Class of Dynamsoft Barcode Reader for Android SDK.
keywords: DCESettingParameters, class, api reference, android
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
pageStartVer: 8.2.1
permalink: /programming/android/api-reference/auxiliary-DCESettingParameters-v8.4.0.html
---

# DCESettingParameters

Stores the DCESettingParameters information.

```java
class com.dynamsoft.dbr.DCESettingParameters;
```

| Attribute | type | Descriptions |
|-----------|------|-------------|
| [`_cameraInstance`](#camerainstance) | *Object* | The Camera Enhancer instance |
| [`_textResultCallback`](#textresultcallback) | [`TextResultCallback`]({{site.android_api}}interface-textresultcallback.html) | Set text result callback. |
| [`_textResultCallback_UserData`](#textresultcallback_userdata) | *Object*  | Transfer user data. |
| [`_intermediateResultCallback`](#intermediateresultcallback) | [`IntermediateResultCallback`]({{site.android_api}}interface-intermediateresultcallback.html) | Set intermediate result callback. |
| [`_intermediateResultCallback_UserData`](#intermediateresultcallback_userdata) | *Object* | Transfer user data. |

## _cameraInstance

The Camera Enhancer instance.

```java
settingParameters._cameraInstance = mCameraEnhancer;
```

## _textResultCallback

Set text result callback.

```java
settingParameters._textResultCallback =mTextResultCallback;
```

**Parameters**

`frameID`: The ID of frame.  
`results`: The recognized barcode result of the frame.  
`userData`: Arguments passed to your function.

## _textResultCallback_UserData

Set the `UserData` of the `_TextResultCallback`.

```java
settingParameters._textResultCallback_UserData =userData;
```

## _intermediateResultCallback

Set intermediate result call back.

```java
settingParameters._intermediateResultCallback = mIntermediateResultCallback;
```

**Parameters**

`frameID`: The ID of frame.  
`results`: The intermediate result of the frame.  
`userData`: Arguments passed to your function.

## _intermediateResultCallback_UserData

Set the `UserData` of the `_IntermediateResultCallback`.

```java
settingParameters._intermediateResultCallback_UserData =userData;
```
