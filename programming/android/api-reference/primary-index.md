---
layout: default-layout
title: BarcodeReader Methods - Dynamsoft Barcode Reader Android API Reference
description: This page shows BarcodeReader methods of Dynamsoft Barcode Reader for Android SDK.
keywords: methods, BarcodeReader, api reference, android
needAutoGenerateSidebar: true
noTitleIndex: true
breadcrumbText: BarcodeReader Class
pageStartVer: 8.6
ignore: true
permalink: /programming/android/api-reference/primary-index.html
---

# BarcodeReader Class

## Initialize

  | Method               | Description |
  |----------------------|-------------|
  | [`BarcodeReader`](primary-initialize-and-destroy.html#barcodereader) | Initialization of `BarcodeReader` object.|

## Video Decoding Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`setCameraEnhancer`](primary-video.html#setcameraenhancer) | Bind a Camera Enhancer instance to the Barcode Reader.  |
  | [`startScanning`](primary-video.html#startscanning) | Start the barcode reading thread. |
  | [`stopScanning`](primary-video.html#stopscanning) | Stop the barcode reading thread. |
  | [`setTextResultListener`](primary-video.html#settextresultlistener) | Set TextResult listener to get result from the callback method when barcode is decoded. |
  | [`setIntermediateResultListener`](primary-video.html#setintermediateresultlistener) | Set intermediateResult listener to get intermediate result from the callback method. |
  | [`setMinImageReadingInterval`](primary-video.html#setminimagereadinginterval) | Set the minimum interval between two barcode decoding. |
  | [`getMinImageReadingInterval`](primary-video.html#getminimagereadinginterval) | Get the minimum interval between two barcode decoding. |
  | [`setImageSource`](primary-video.html#setimagesource) | Set the ImageSource as the source of video streaming. |
  | [`enableResultVerification`](primary-video.html#enableresultverification) | Enable **Result Verification** feature to improve the accuracy of barcode results for video streaming barcode decoding. |
  | [`enableDuplicateFilter`](primary-video.html#enableduplicatefilter) | Enable **Duplicate Filter** feature to filter out the duplicate results in the period of `duplicateForgetTime` for video barcode decoding. |
  | [`setDuplicateForgetTime`](primary-video.html#setduplicateforgettime) | Set the property of `duplicateForgetTime`, Default value is 3000(ms). |
  | [`getDuplicateForgetTime`](primary-video.html#getduplicateforgettime) | Get the property of `duplicateForgetTime`. |

> Note:
>
> - `setTextResultCallback` is deprecated, please use `setTextResultListener` instead.
> - `setIntermediateResultCallback` is deprecated, please use `setIntermediateResultListener` instead.

## Image Decoding Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`decodeBuffer`](primary-decode.html#decodebuffer) | Decode barcodes from raw buffer. |
  | [`decodeFile`](primary-decode.html#decodefile) | Decode barcodes from a specified image file. |
  | [`decodeFileInMemory`](primary-decode.html#decodefileinmemory) | Decode barcodes from an image file in memory. |
  | [`decodeBase64String`](primary-decode.html#decodebase64string) | Decode barcodes from a base64 encoded string. |
  | [`decodeBufferedImage`](primary-decode.html#decodeBufferedImage) | Decodes barcode from a buffered image (bitmap). |

## License

  | Method               | Description |
  |----------------------|-------------|
  | [`initLicense`](primary-license.html#initlicense) | Read product key and activate the SDK. |
  | [`setDeviceFriendlyName`](primary-license.html#setdevicefriendlyname) | Sets a human-readable name that identifies the device. |

> Note:  
>  
> The following license activation methods are deprecated:
>
> - `outputLicenseToString`
> - `initLicenseFromDLS`
> - `initLicenseFromServer`
> - `initLicenseFromLicenseContent`
> Please use [`initLicense`](primary-license.html#initlicense) instead.

## Parameter and Runtime Settings

### Basic

  | Method               | Description |
  |----------------------|-------------|
  | [`getRuntimeSettings`](primary-parameter-and-runtime-settings-basic.html#getruntimesettings) | Get current runtime settings. |
  | [`updateRuntimeSettings (with struct)`](primary-parameter-and-runtime-settings-basic.html#updateruntimesettings) | Modify and update the current runtime settings. |
  | [`updateRuntimeSettings (with preset template)`](primary-parameter-and-runtime-settings-basic.html#with-a-preset-template) | Update runtime settings from one of the preset templates. |
  | [`resetRuntimeSettings`](primary-parameter-and-runtime-settings-basic.html#resetruntimesettings) | Reset runtime settings to default. |

### Advanced
  
  | Method               | Description |
  |----------------------|-------------|
  | [`initRuntimeSettingsWithFile`](primary-parameter-and-runtime-settings-advanced.html#initruntimesettingswithfile)  | Initialize runtime settings with the settings in a given JSON file. |
  | [`initRuntimeSettingsWithString`](primary-parameter-and-runtime-settings-advanced.html#initruntimesettingswithstring) | Initialize runtime settings with the settings in a given JSON string. |
  | [`appendTplFileToRuntimeSettings`](primary-parameter-and-runtime-settings-advanced.html#appendtplfiletoruntimesettings) | Append a new template file to the current runtime settings. |
  | [`appendTplStringToRuntimeSettings`](primary-parameter-and-runtime-settings-advanced.html#appendtplstringtoruntimesettings) | Append a new template string to the current runtime settings. |
  | [`getAllParameterTemplateNames`](primary-parameter-and-runtime-settings-advanced.html#getallparametertemplatenames) | Gets the parameter templates name array. |
  | [`outputSettingsToFile`](primary-parameter-and-runtime-settings-advanced.html#outputsettingstofile) | Output runtime settings to a settings file (JSON file). |
  | [`outputSettingsToString`](primary-parameter-and-runtime-settings-advanced.html#outputsettingstostring) | Output runtime settings to a string. |
  | [`setModeArgument`](primary-parameter-and-runtime-settings-advanced.html#setmodeargument) | Set argument value for the specified mode parameter. |
  | [`getModeArgument`](primary-parameter-and-runtime-settings-advanced.html#getmodeargument) | Get argument value for the specified mode parameter. |

## Result

  | Method               | Description |
  |----------------------|-------------|
  | [`initIntermediateResult`](primary-result.html#initintermediateresult) | Inits an intermediateResult struct with default values. |
  | [`getIntermediateResults`](primary-result.html#getintermediateresults) | Get intermediate results. |
  | [`decodeIntermediateResults`](primary-result.html#decodeintermediateresults) | Decodes barcode from intermediate results. |

## Status Retrieval

  | Method               | Description |
  |----------------------|-------------|
  | [`getVersion`](primary-status-retrieval.html#getversion) | Get version information of SDK.|
  | [`setLogConfig`](primary-status-retrieval.html#setlogconfig) | Set the directory and the saving mode of log. It helps you on debugging. |
