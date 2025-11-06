---
layout: default-layout
title: BarcodeScannerConfig Class - Dynamsoft Barcode Reader Flutter Edition
description: BarcodeScannerConfig of DynamsoftBarcodeReader Flutter is the class that defines the configurations for Barcode scanning.
keywords: Barcode, scanner, config, flutter 
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: BarcodeScannerConfig
---

# BarcodeScannerConfig Class

`BarcodeScannerConfig` is the class that defines the configurations for the Barcode Scanner. Please see the [code snippet](#code-snippet) section for the full usage of this class.

## Definition

*Assembly:* dynamsoft_barcode_reader_bundle_flutter

```dart
class BarcodeScannerConfig
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`license`](#license) | *string* | Represents the Barcode Reader license string. |
| [`templateFile`](#templatefile) | *string* | Specifies the template configuration with a file path or a JSON string. |
| [`isTorchButtonVisible`](#istorchbuttonvisible) | *bool* | Determines the visibility status of the torch (flashlight) button of the UI. |
| [`isBeepEnabled`](#isbeepenabled) | *bool* |  Establishes whether a beep sound is played when a barcode is successfully detected. |
| [`isVibrateEnabled`](#isvibrateenabled) | *bool* |  Determines if the phone will vibrate once a barcode is successfully detected. |
| [`isCloseButtonVisible`](#isclosebuttonvisible) | *bool* | Toggles the visibility of the close button. |
| [`isGuideFrameVisible`](#isguideframevisible) | *bool* | Indicates the visibility status of the guide frame on the display. |
| [`isCameraToggleButtonVisible`](#iscameratogglebuttonvisible) | *bool* | Determines the visibility status of the camera toggle button that is used to switch between the rear and front cameras.  |
| [`scanRegion`](#scanregion) | *DMRect?* | Specifies the region that the scanner will focus on and decode barcodes from. |
| [`isScanLaserVisible`](#isscanlaservisible) | *bool* | Enables/Disables the visibility status of the scan laser. |
| [`isAutoZoomEnabled`](#isautozoomenabled) | *bool* | Enables/Disables the auto zoom feature of the camera. |
| [`barcodeFormats`](#barcodeformats) | *EnumBarcodeFormat* | Defines the barcode format(s) that the BarcodeScanner instance will be able to read. |
| [`scanningMode`](#scanningmode) | *EnumScanningMode* | Determines whether the Barcode Scanner will be operating in single-scan or multiple-scan mode. |
| [`maxConsecutiveStableFramesToExit`](#maxconsecutivestableframestoexit) | *int* | Specifies the maximum number of consecutive stable frames to process before finishing the scan process. |
| [`expectedBarcodesCount`](#expectedbarcodescount) | *int* | Defines the expected number of barcodes to be scanned in a single frame or image. |

> [!NOTE]
> Please note that all of the properties above are Getter/Setter pairs.

### license

Represents the Barcode Reader license string.

```dart
String license;
```

### templateFile

Specifies the template configuration with a file path or a JSON string that defines the various Barcode Reader parameters. Please see this [page]({{ site.programming }}features/use-runtimesettings-or-templates.html?lang=objc,swift#json-template) for more info on how to create your own template.

```dart
String? templateFile;
```

**Remarks**

If you are choosing to use a JSON string directly, please note that it will need to be in the proper format. Once you have the JSON template completed, you must remove all the white spaces and then stringify the content of the JSON template in order to get the JSON string. Please see this [section](../../foundational-user-guide.md#using-a-json-template) of the foundational user guide to see how the JSON string needs to look like in order to not throw any errors.

### isTorchButtonVisible

Determines the visibility status of the torch (flashlight) button of the UI. If set to `true`, the torch button will be displayed - enabling users to turn the flashlight on/off. Default is `true`.

```dart
bool isTorchButtonVisible;
```

### isBeepEnabled

Establishes whether a beep sound is played when a barcode is successfully detected. If set to `true`, a beep will be played once a barcode is successfully detected. Default is `false`.

```dart
bool isBeepEnabled;
```

### isVibrateEnabled

Determines if the phone will provide haptic feedback once a barcode is successfully detected. If set to `true`, the phone will give off a small vibration to indicate that a barcode was successfully recognized. Default is `false`.

```dart
bool isVibrateEnabled;
```

### isCloseButtonVisible

Toggles the visibility of the close button. If set to `true`, a close button will appear on the top-right corner of the UI to allow the user to close the camera view. If the scanner is closed before a scan is finished, the `status` of the [`BarcodeScanResult`](barcode-scan-result.md) will be `EnumResultStatus.canceled`. Default is `true`.

```dart
bool isCloseButtonVisible;
```

### isCameraToggleButtonVisible

Determines the visibility status of the camera toggle button that is used to switch between the rear and front cameras. If set to `true`, a button will show up on the bottom-right to allow the user to switch to the front camera (since the default is the rear camera). Default is `false`.

```dart
bool isCameraToggleButtonVisible;
```

### scanRegion

Specifies the region (as a [`DSRect`]({{ site.dcv_flutter_api }}core/dsrect.html)) that the scanner will focus on and decode barcodes from. The default scan region is the full area of the image/frame.  

```dart
DSRect? scanRegion;
```

**Remarks**

[`DSRect`]({{ site.dcv_flutter_api }}core/dsrect.html) is represented with a `top`, `left`, `right`, and `bottom`. The axes that are used to find these borders start from the top-left most point of the image/frame, with the x-axis going left to right and the y-axis going top to bottom. `measuredInPercentage` is the last parameter of `DSRect` - and it determines if the dimensions should be represented as percentages of the frame or not. We recommend to set this to `true` to simplify the process.

- `top` represents the distance between the x-axis and the top-most point of the Rect.
- `bottom` represents the distance between the x-axis and the bottom-most point of the Rect.
- `left` represents the distance between the y-axis the left-most point of the Rect.
- `right` represents the distance between the y-axis and the right-most point of the Rect.

```dart
final scanRegion = DSRect(left: 0.1, top: 0.4, right: 0.9, bottom: 0.6, measuredInPercentage: true);
```

> [!NOTE]
> Starting with the horizontal part of the scan region - the one above sets the left border of the region 10% away from the y-axis and the right border 90% away from the y-axis. And for the vertical part of the scan region - this one sets the top border 40% away from the x-axis and the bottom border 60% away from the x-axis. 

### isScanLaserVisible

Enables/Disables the visibility status of the scan laser. The scan laser is just a visual light bar that moves up and down to indicate that the scan process is taking place - it does not affect the performance in any way. Default is `true`.

```dart
bool IsScanLaserVisible;
```

### isAutoZoomEnabled

Enables/Disables the auto zoom feature of the camera. When enabled (true), the scanner will automatically zoom in when attempting to scan a barcode that it can vaguely localize, but not fully. Zooming in allows the library to more accurately detect the barcode. This is especially helpful in scenarios where there is some distance between the barcode and the camera. Default is `false`.

```dart
bool IsAutoZoomEnabled;
```

### barcodeFormats

Defines the barcode format(s) (represented as [`EnumBarcodeFormat`](../enum/barcode-format.md)) that the BarcodeScanner instance will be able to read.

```dart
EnumBarcodeFormat barcodeFormats;
```

#### Remarks

In order to set multiple barcode formats, please use the `|` (OR) operator as such `barcodeFormats: EnumBarcodeFormat.BF_QR_CODE | EnumBarcodeFormat.BF_ONED,`

### scanningMode

Determines whether the Barcode Scanner will be operating in single-scan or multiple-scan mode (represented as a [`EnumScanningMode`](../enum/scanning-mode.md)). `EnumScanningMode.single` means that the scanner can recognize only one barcode at a time. `EnumScanningMode.multiple` allows for continuous scanning and for the scanner to recognize multiple barcodes in a single frame. Default value is `EnumScanningMode.single`.

```dart
EnumScanningMode scanningMode;
```

### maxConsecutiveStableFramesToExit

Specifies the maximum number of consecutive stable frames to process before finishing the scan process. A *stable frame* is one where no new barcode is detected. Default value is 10.

```dart
int maxConsecutiveStableFramesToExit;
```

### expectedBarcodesCount

Defines the expected number of barcodes to be scanned in a single frame or image. Default value is 999.

```dart
int expectedBarcodesCount;
```

#### Remarks

- 0: detects at least one barcode.
- N ( N > 0 ): detects N barcodes.
- Dynamsoft Barcode Reader works as a loop trying different parameters to detect as many barcodes as possible till it reaches the nuumber specified by expectedBarcodesCount. If expectedBarcodesCount is 0, the loop stops after a cycle finishes and detects at least one barcode. If ExpectedBarcodesCount is N, the loop stops once N barcodes are detected.

## How to use BarcodeScannerConfig

```dart
const config = BarcodeScannerConfig(
  
  ///The license key required to initialize the BarcodeScanner.
  license: "DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9", //The license string here grants a time-limited free trial which requires network connection to work.
  
  ///Sets the barcode format(s) to read.
  ///This value is a combination of EnumBarcodeFormat flags that determine which barcode types to read.
  ///For example, to scan QR codes and OneD codes,
  ///set the value to `EnumBarcodeFormat.qrCode | EnumBarcodeFormat.oned`.
  barcodeFormats: EnumBarcodeFormat.qrCode | EnumBarcodeFormat.oned,
  
  ///Defines the scanning area as a DSRect object where barcodes will be detected.
  ///Only the barcodes located within this defined region will be processed. 
  ///Default is undefined, which means the full screen will be scanned.
  scanRegion: DSRect(top: 0.25, bottom: 0.75, left: 0.25, right: 0.75, measuredInPercentage: true), // scan the middle 50% of the screen
  
  ///Determines whether the torch (flashlight) button is visible in the scanning UI.
  ///Set to true to display the torch button, enabling users to turn the flashlight on/off. Default is true.
  isTorchButtonVisible: true,

  ///Specifies if a beep sound should be played when a barcode is successfully detected.
  ///Set to true to enable the beep sound, or false to disable it. Default is false.
  isBeepEnabled: false,

  ///Determines if the phone will provide haptic feedback once a barcode is successfully detected.
  ///Set to true to make the phone vibrate once a barcode is found. Default is false.
  isVibrateEnabled: true,

  ///Enables or disables the auto-zoom feature during scanning.
  ///When enabled (true), the scanner will automatically zoom in to improve barcode detection. Default is false.
  isAutoZoomEnabled: false,

  ///Determines whether the close button is visible on the scanner UI.
  ///This button allows users to exit the scanning interface. Default is true.
  isCloseButtonVisible: true,

  ///Specifies whether the camera toggle button is displayed.
  ///This button lets users switch between available cameras (e.g., front and rear). Default is false.
  isCameraToggleButtonVisible: false,

  ///Determines if a scanning laser overlay is shown on the scanning screen.
  ///This visual aid (scan laser) helps indicate the scanning line during barcode detection. Default is true.
  isScanLaserVisible: true,

  ///Sets the scanning mode for the BarcodeScanner.
  ///The mode is defined by the EnumScanningMode and affects the scanning behavior. Default is `EnumScanningMode.single`.
  scanningMode: EnumScanningMode.single,

  ///Defines the expected number of barcodes to be scanned.
  ///The scanning process will automatically stop when the number of detected barcodes reaches this count.
  ///Only available when `scanningMode` is set to `EnumScanningMode.multiple`. Default is 999.
  expectedBarcodesCount: 999,

  ///Specifies the maximum number of consecutive stable frames to process before exiting scanning.
  ///A "stable frame" is one where no new barcode is detected.
  ///Only available when `scanningMode` is set to `EnumScanningMode.multiple`. Default is 10.
  maxConsecutiveStableFramesToExit: 10,

  ///Specifies the template configuration for the BarcodeScanner.
  ///This can be either a file path or a JSON string that defines various scanning parameters.
  ///Default is undefined, which means the default template will be used.
  templateFile: "JSON template as string OR path to JSON template file",
);
```