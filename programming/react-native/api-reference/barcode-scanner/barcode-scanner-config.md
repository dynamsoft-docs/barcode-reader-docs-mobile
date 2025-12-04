---
layout: default-layout
title: BarcodeScannerConfig Class - Dynamsoft Barcode Reader React Native Edition
description: BarcodeScannerConfig of DynamsoftBarcodeReader React Native is the class that defines the configurations for Barcode scanning.
keywords: Barcode, scanner, config, flutter 
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: BarcodeScannerConfig
---

# BarcodeScannerConfig Class

`BarcodeScannerConfig` is the class that defines the configurations for the Barcode Scanner.

## Definition

*Assembly:* dynamsoft-barcode-reader-bundle-react-native

```js
interface BarcodeScanConfig
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`license`](#license) | *string* | Represents the Barcode Reader license string. |
| [`templateFile`](#templatefile) | *string* | Specifies the template configuration with a file path or a JSON string. |
| [`isTorchButtonVisible`](#istorchbuttonvisible) | *boolean* | Determines the visibility status of the torch (flashlight) button of the UI. |
| [`isBeepEnabled`](#isbeepenabled) | *boolean* |  Establishes whether a beep sound is played when a barcode is successfully detected. |
| [`isVibrateEnabled`](#isvibrateenabled) | *boolean* |  Determines if the phone will vibrate once a barcode is successfully detected. |
| [`isCloseButtonVisible`](#isclosebuttonvisible) | *boolean* | Toggles the visibility of the close button. |
| [`isGuideFrameVisible`](#isguideframevisible) | *boolean* | Indicates the visibility status of the guide frame on the display. |
| [`isCameraToggleButtonVisible`](#iscameratogglebuttonvisible) | *boolean* | Determines the visibility status of the camera toggle button that is used to switch between the rear and front cameras.  |
| [`scanRegion`](#scanregion) | *DMRect?* | Specifies the region that the scanner will focus on and decode barcodes from. |
| [`isScanLaserVisible`](#isscanlaservisible) | *boolean* | Enables/Disables the visibility status of the scan laser. |
| [`isAutoZoomEnabled`](#isautozoomenabled) | *boolean* | Enables/Disables the auto zoom feature of the camera. |
| [`barcodeFormats`](#barcodeformats) | *[EnumBarcodeFormat](../barcode-reader/enum/barcode-format.md)* | Defines the barcode format(s) that the BarcodeScanner instance will be able to read. |
| [`scanningMode`](#scanningmode) | *[EnumScanningMode](enum/scanning-mode.md)* | Determines whether the Barcode Scanner will be operating in single-scan or multiple-scan mode. |
| [`maxConsecutiveStableFramesToExit`](#maxconsecutivestableframestoexit) | *int* | Specifies the maximum number of consecutive stable frames to process before finishing the scan process. |
| [`expectedBarcodesCount`](#expectedbarcodescount) | *int* | Defines the expected number of barcodes to be scanned in a single frame or image. |
| [`templateNodeRequire`](#templatenoderequire) | *NodeRequire* | Provides a Node.js 'require' function to load the template file when running in a Node environment. |

### license

Represents the Barcode Reader license string.

```js
license?: string;
```

### templateFile

Specifies the template configuration with a file path or a JSON string that defines the various Barcode Reader parameters. Please see this [page]({{ site.programming }}features/use-runtimesettings-or-templates.html?lang=objc,swift#json-template) for more info on how to create your own template.

```js
templateFile?: string;
```

**Remarks**

If you are choosing to use a JSON string directly, please note that it will need to be in the proper format. Once you have the JSON template completed, you must remove all the white spaces and then stringify the content of the JSON template in order to get the JSON string. Please see this [section](../../foundational-user-guide.md#using-a-json-template) of the foundational user guide to see how the JSON string needs to look like in order to not throw any errors.

### isTorchButtonVisible

Determines the visibility status of the torch (flashlight) button of the UI. If set to `true`, the torch button will be displayed - enabling users to turn the flashlight on/off. Default is `true`.

```js
isTorchButtonVisible?: booleanean;
```

### isBeepEnabled

Establishes whether a beep sound is played when a barcode is successfully detected. If set to `true`, a beep will be played once a barcode is successfully detected. Default is `false`.

```js
isBeepEnabled?: booleanean;
```

### isVibrateEnabled

Determines if the phone will provide haptic feedback once a barcode is successfully detected. If set to `true`, the phone will give off a small vibration to indicate that a barcode was successfully recognized. Default is `false`.

```js
isVibrateEnabled?: booleanean;
```

### isCloseButtonVisible

Toggles the visibility of the close button. If set to `true`, a close button will appear on the top-right corner of the UI to allow the user to close the camera view. If the scanner is closed before a scan is finished, the `status` of the [`BarcodeScanResult`](barcode-scan-result.md) will be `EnumResultStatus.canceled`. Default is `true`.

```js
isCloseButtonVisible?: booleanean;
```

### isCameraToggleButtonVisible

Determines the visibility status of the camera toggle button that is used to switch between the rear and front cameras. If set to `true`, a button will show up on the bottom-right to allow the user to switch to the front camera (since the default is the rear camera). Default is `false`.

```js
isCameraToggleButtonVisible?: booleanean;
```

### scanRegion

Specifies the region (as a [`DSRect`]({{ site.dcv_react_native_api }}core/dsrect.html)) that the scanner will focus on and decode barcodes from. The default scan region is the full area of the image/frame.  

```js
scanRegion?: DSRect;
```

**Remarks**

[`DSRect`]({{ site.dcv_react_native_api }}core/dsrect.html) is represented with a `top`, `left`, `right`, and `bottom`. The axes that are used to find these borders start from the top-left most point of the image/frame, with the x-axis going left to right and the y-axis going top to bottom. `measuredInPercentage` is the last parameter of `DSRect` - and it determines if the dimensions should be represented as percentages of the frame or not. We recommend to set this to `true` to simplify the process.

- `top` represents the distance between the x-axis and the top-most point of the Rect.
- `bottom` represents the distance between the x-axis and the bottom-most point of the Rect.
- `left` represents the distance between the y-axis the left-most point of the Rect.
- `right` represents the distance between the y-axis and the right-most point of the Rect.

### isScanLaserVisible

Enables/Disables the visibility status of the scan laser. The scan laser is just a visual light bar that moves up and down to indicate that the scan process is taking place - it does not affect the performance in any way. Default is `true`.

```js
isScanLaserVisible?: booleanean;
```

### isAutoZoomEnabled

Enables/Disables the auto zoom feature of the camera. When enabled (true), the scanner will automatically zoom in when attempting to scan a barcode that it can vaguely localize, but not fully. Zooming in allows the library to more accurately detect the barcode. This is especially helpful in scenarios where there is some distance between the barcode and the camera. Default is `false`.

```js
isAutoZoomEnabled?: booleanean;
```

### barcodeFormats

Defines the barcode format(s) (represented as [`EnumBarcodeFormat`](../enum/barcode-format.md)) that the BarcodeScanner instance will be able to read.

```js
barcodeFormats?: bigint;
```

#### Remarks

In order to set multiple barcode formats, please use the `|` (OR) operator as such `barcodeFormats: EnumBarcodeFormat.BF_QR_CODE | EnumBarcodeFormat.BF_ONED,`

### scanningMode

Determines whether the Barcode Scanner will be operating in single-scan or multiple-scan mode (represented as a [`EnumScanningMode`](../enum/scanning-mode.md)). `EnumScanningMode.single` means that the scanner can recognize only one barcode at a time. `EnumScanningMode.multiple` allows for continuous scanning and for the scanner to recognize multiple barcodes in a single frame. Default value is `EnumScanningMode.single`.

```js
scanningMode?: EnumScanningMode;
```

### maxConsecutiveStableFramesToExit

Specifies the maximum number of consecutive stable frames to process before finishing the scan process. A *stable frame* is one where no new barcode is detected. Default value is 10.

```js
maxConsecutiveStableFramesToExit?: number;
```

### expectedBarcodesCount

Defines the expected number of barcodes to be scanned in a single frame or image. Default value is 999.

```js
expectedBarcodesCount?: number;
```

#### Remarks

- 0: detects at least one barcode.
- N ( N > 0 ): detects N barcodes.
- Dynamsoft Barcode Reader works as a loop trying different parameters to detect as many barcodes as possible till it reaches the nuumber specified by expectedBarcodesCount. If expectedBarcodesCount is 0, the loop stops after a cycle finishes and detects at least one barcode. If ExpectedBarcodesCount is N, the loop stops once N barcodes are detected.

### templateNodeRequire

Provides a Node.js 'require' function to load the template file when running in a Node environment. This facilitates importing external template configuration files.

```js
templateNodeRequire?: NodeRequire;
```
