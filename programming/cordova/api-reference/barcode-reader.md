---
layout: default-layout
title: Class DCVBarcodeReader of Dynamsoft Capture Vision Cordova Edition
description: This page is the API reference of Class DCVBarcodeReader
keywords: Class DCVBarcodeReader, API Reference, Cordova
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: Class DCVBarcodeReader
---

# Class DCVBarcodeReader

`DCVBarcodeReader` accesses the camera via a `DCVCameraView` object at the native level, then perform continuous barcode scanning on the incoming frames.

```js
class DCVBarcodeReader
```

| Method | Description |
| ------- | ----------- |
| [`createInstance`](#createinstance) | Create an instance of `DCVBarcodeReader`. |
| [`initLicense`](#initlicense) | Initialize the license of Dynamsoft Barcode Reader. |
| [`getVersion`](#getversion) | Get the version of `DCVBarcodeReader`, which is packaged in Dynamsoft Capture Vision. |
| [`getRuntimeSettings`](#getruntimesettings) | Get the current runtime settings of `DCVBarcodeReader`. |
| [`updateRuntimeSettings`](#updateruntimesettings) | Update the runtime settings of `DCVBarcodeReader` with a DBRRuntimeSettings object, a preset template or a JSON String. |
| [`resetRuntimeSettings`](#resetruntimesettings) | Reset the runtime settings of `DCVBarcodeReader` to default. |
| [`outputRuntimeSettingsToString`](#outputruntimesettingstostring) | Output the runtime settings of `DCVBarcodeReader` to string. |
| [`startScanning`](#startscanning) | Start the barcode decoding thread. |
| [`stopScanning`](#stopscanning) | Stop the barcode decoding thread. |
| [`addResultListener`](#addresultlistener) | Specifies an event handler that fires after the library finishes scanning a frame. |

## createInstance

Create an instance of `DCVBarcodeReader`.

```js
static createInstance(): Promise<DCVBarcodeReader>;
```

**Return Value**

An instance of `DCVBarcodeReader`.

**Code Snippet**

```js
dbr = await Dynamsoft.DCVBarcodeReader.createInstance()
```

## initLicense

Initialize the license of the Barcode Reader module.

```js
static initLicense(license: String): Promise<void>;  
```

**Parameters**

`license`: A license key.

**Code Snippet**

```js
try {
    await Dynamsoft.DCVBarcodeReader.initLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9");
} catch (e) {
    console.log(e)
}
```

## getVersion

Get the version of `DCVBarcodeReader`, which is packaged in Dynamsoft Capture Vision.

```js
static getVersion(): Promise<string>;
```

**Return Value**

The Version of `DCVBarcodeReader`.

## getRuntimeSettings

Get the current runtime settings of `DCVBarcodeReader`.

```js
getRuntimeSettings(): Promise<DBRRuntimeSettings>;
```

**Return Value**

An object of [`DBRRuntimeSettings`](interface-dbr-runtime-settings.md) that stores the runtime settings.

**Code Snippet**

```js
let settings = await dbr.getRuntimeSettings();
```

## updateRuntimeSettings

Update the barcode decoding settings with a [`DBRRuntimeSettings`](interface-dbr-runtime-settings.md) struct, a preset template (from the [`EnumDBRPresetTemplate`](enum-dbr-preset-template.md) items) or a JSON String.

```js
updateRuntimeSettings(settings: String | DBRRuntimeSettings | EnumDBRPresetTemplate): Promise<void>;
```

**Parameters**

`Settings`: The parameter should be one of the following types:

- `settings (DBRRuntimeSettings)`: An object that stores `DBRRuntimeSettings`.  
- `settings (EnumDBRPresetTemplate)`: One of the `EnumDBRPresetTemplate` member that indicates a preset template.  
- `settings (String)`: A stringified JSON data that contains barcode decoding settings. The available settings include but not limited in `DBRRuntimeSettings`. You can access full feature of DBR when upload the settings from a JSON data.

**Code Snippet**

```js
// Update runtime settings from a DBRRuntimeSettings object.
let settings = await dbr.getRuntimeSettings()
settings.expectedBarcodesCount = 5;
settings.timeout = 1000;
dbr.updateRuntimeSettings(settings)
// Update runtime settings from a preset template
dbr.updateRuntimeSettings(Dynamsoft.EnumDBRPresetTemplate.VIDEO_SPEED_FIRST)
// Update runtime settings from a JSON template.
dbr.updateRuntimeSettings("{\"ImageParameter\":{\"BarcodeFormatIds\":[\"BF_ALL\"],\"BarcodeFormatIds_2\":null,\"DeblurLevel\":0,\"ExpectedBarcodesCount\":0,\"LocalizationModes\":[{\"Mode\":\"LM_SCAN_DIRECTLY\",\"ScanDirection\":1},{\"Mode\":\"LM_CONNECTED_BLOCKS\"}],\"Name\":\"video-speed-first\",\"ScaleDownThreshold\":2300,\"Timeout\":500},\"Version\":\"3.0\"}")
```

## resetRuntimeSettings

Reset the barcode decoding settings to default value.

```js
resetRuntimeSettings(): void;
```

## outputRuntimeSettingsToString

Output the barcode decoding settings to string.

```js
outputRuntimeSettingsToString(): Promise<string>;
```

**Return Value**

A string that stores the barcode decoding settings. The barcode settings string can be applied to debug barcode decoding settings.

## startScanning

Start the barcode decoding thread.

```js
startScanning(): void;
```

## stopScanning

Stop the barcode decoding thread.

```js
stopScanning(): void;
```

## addResultListener

Specifies an event handler that fires after the library finishes scanning a frame.

```js
addResultListener(listener: (results: BarcodeResult[]) => void): void;
```

**Code Snippet**

The following code snippet shows how to use barcode reader module to decode from video stream.

```js
dbr.addResultListener((results) => {
    const resultElement = document.getElementById('show_result');
    var resultStr = ""
    if (results && results.length > 0) {
        for (i = 0; i < results.length; i++) {
            resultStr=resultStr + results[i].barcodeFormatString+":"+results[i].barcodeText+'\n'
        }
        resultElement.innerHTML = (resultStr)
    } else {
        resultElement.innerHTML = "No barcode detected in this frame."
    }
    document.querySelector('#camera_view').appendChild(resultElement)
})
```

### setMinImageReadingInterval

Set the minimum image reading interval.

```js
setMinImageReadingInterval(interval: number): void;
```

### getMinImageReadingInterval

Get the minimum image reading interval.

```js
getMinImageReadingInterval(): Promise<number>;
```
