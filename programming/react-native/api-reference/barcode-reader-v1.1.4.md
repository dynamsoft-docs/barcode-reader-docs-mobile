---
layout: default-layout
title: Barcode Reader Class - Dynamsoft Capture Vision React Native Edition
description: This page is the API reference of Barcode Reader class
keywords: Barcode, API reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: Barcode Reader class
---

# DynamsoftBarcodeReader Class

A barcode reader object accesses to a camera via DynamsoftCameraView object at native level, then perform continuous barcode scanning on the incoming frames.

| Methods | Description |
| ------- | ----------- |
| [`initLicense`](#initlicense) | Initialize the license of the Dynamsoft Barcode Reader module. |
| [`createInstance`](#createinstance) | Create a barcode reader instance. |
| [`getVersion`](#getversion) | Get the version of `DynamsoftBarcodeReader`, which is packaged in Dynamsoft Capture Vision. |
| [`getRuntimeSettings`](#getruntimesettings) | Get the current runtime settings of `DynamsoftBarcodeReader`. |
| [`updateRuntimeSettings`](#updateruntimesettings) | Update the runtime settings of `DynamsoftBarcodeReader` with a `DBRRuntimeSettings` struct or a template. |
| [`resetRuntimeSettings`](#resetruntimesettings) | Reset the runtime settings of `DynamsoftBarcodeReader` to default. |
| [`outputRuntimeSettingsToString`](#outputruntimesettingstostring) | Output the runtime settings of `DynamsoftBarcodeReader` to string. |
| [`startScanning`](#startscanning) | Start the barcode decoding thread. |
| [`stopScanning`](#stopscanning) | Stop the barcode decoding thread. |
| [`addResultListener`](#addresultlistener) | Specifies an event handler that fires after the library finishes scanning a frame. |
| [`removeAllResultListeners`](#removeallresultlisteners) | Remove all existing result listener. |

## initLicense

Initialize the license of Dynamsoft Capture Vision - Barcode Reader Module.

```js
static initLicense(license: String): Promise<void>;
```

**Parameters**

`license`: A license key.

**Code Snippet**

```js
try {
  await DynamsoftBarcodeReader.initLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9")
} catch (e) {
  // Catch and log the error message when license activation is failed.
  console.log(e)
}
```

## createInstance

Create a barcode reader instance.

```js
static createInstance(): Promise<DynamsoftBarcodeReader>
```

**Return Value**

A barcode reader instance.

**Code Snippet**

```js
this.reader = await DynamsoftBarcodeReader.createInstance();
```

## getVersion

Get the version of `DynamsoftBarcodeReader`, which is packaged in Dynamsoft Capture Vision.

```js
getVersion(): Promise<string>
```

**Return Value**

The Version of `DynamsoftBarcodeReader`.

**Code Snippet**

```js
let dbrVersion = await this.reader.getVersion();
```

## getRuntimeSettings

Get the current runtime settings of `DynamsoftBarcodeReader`.

```js
getRuntimeSettings(): Promise<DBRRuntimeSettings>
```

**Return Value**

An object that stores the runtime settings.

**Code Snippet**

```js
let settings = await this.reader.getRuntimeSettings();
```

## updateRuntimeSettings

Update the barcode decoding settings with a `DBRRuntimeSettings` struct or a template.

```js
updateRuntimeSettings(settings: DBRRuntimeSettings | EnumDBRPresetTemplate | String): Promise<boolean>
```

**Parameters**

`Settings`: The parameter should be one of the following types:

- An object that stores barcode reader runtime settings.
- A JSON string that stores the barcode reader template.
- An enumeration member of [EnumPresetTemplate](../api-reference/enum-dbr-preset-template.md)

**Code Snippet**

```js
/* How to update using one of the preset templates */
await this.reader.updateRuntimeSettings(EnumDBRPresetTemplate.VIDEO_SPEED_FIRST);

/* How to update runtime settings using runtime settings object */
let settings = await this.reader.getRuntimeSettings();
settings.barcodeFormatIds = EnumBarcodeFormat.BF_ONED | EnumBarcodeFormat.BF_QR_CODE;
settings.expectedBarcodeCount = 1;
await this.reader.updateRuntimeSettings(settings);
```

## resetRuntimeSettings

Reset the barcode decoding settings.

```js
resetRuntimeSettings(): Promise<boolean>
```

**Code Snippet**

```js
await this.reader.resetRuntimeSettings();
```

## outputRuntimeSettingsToString

Output the barcode decoding settings to string.

```js
outputRuntimeSettingsToString(): Promise<string>
```

**Return Value**

A string that stores the barcode decoding settings. The barcode settings string can be applied to debug barcode decoding settings.

**Code Snippet**

```js
let settingString = await this.reader.outputRuntimeSettingsToString();
```

## startScanning

Start the barcode decoding thread.

```js
startScanning(): Promise<void>
```

**Code Snippet**

```js
await this.reader.startScanning();
```

## stopScanning

Stop the barcode decoding thread.

```js
stopScanning(): Promise<void>
```

**Code Snippet**

```js
await this.reader.stopScanning();
```

## addResultListener

Specifies an event handler that fires after the library finishes scanning a frame.

```js
addResultListener(listener: (results: BarcodeResult[]) => void): void
```

**Parameters**

`listener`: The event listener that handles callback when barcode result is returned by the library.

**Code Snippet**

```js
state = {
  results: null
};
componentDidMount() {
  (async () => {
    try {
      await DynamsoftBarcodeReader.initLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9")
    } catch (e) {
      console.log(e);
    }
    this.reader = await DynamsoftBarcodeReader.createInstance();
    await this.reader.startScanning();
    this.reader.addResultListener((results) => {
      this.setState({results});
    });
  })();
}
```

## removeAllResultListeners

Remove all existing result listener.

```js
removeAllResultListeners(): void;
```

**Code Snippet**

```js
async componentWillUnmount() {
  ...
  // Remove the result listener when your component is unmount.
  this.reader.removeAllResultListeners()
}
```
